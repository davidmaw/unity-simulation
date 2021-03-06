This repository hosts a barely functional version of the tanda-pay-simulation project, with no references to TandaPay, and only contains Unity.
The Unity simulation's number-crunching logic is found in src/app/service/unity.simulation.service.ts. The rules of Unity are laid out in that script, and it depends on src/app/model/policy-holder.ts and src/app/model/unity-state.ts to store state and model decisions. I strongly recommend that a web developer who has their own toolkit for designing websites to scrap everything but the logic contained in the aforementioned files

-policy-holder.ts contains the PolicyHolder class, which encapsulates the decisions/unique attributes of the Unity policyholders. When the simulation needs policyholders to make a decision, it calls functions from this class.

-unity-state.ts contains the UnityState class, which is just a class that contains fields that unity.simulation.service.ts cares about. An array of PolicyHolder objects and an instance of a UnityState should completely store all of the information of a Unity simulation.

-src/app/model/user-input.ts has a class which contains fields for all of the settings that goes into initializing a simulation

-src/app/service/simulation.setup.service.ts processes a userInput instance an initializes policyholders and simulation state accordingly

The rest of the repository contains Angular modules/building-blocks for binding the web application to the settings and simulation data.
