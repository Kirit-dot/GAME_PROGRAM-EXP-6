# GAME_PROGRAM-EXP-6
## AIM
To create an AI character in Unreal Engine that roams randomly within a NavMesh area and chases the player when they come within a certain range, using Behavior Trees, Blackboard, and AI Perception.
## Procedure
 Setup Navigation:
• Add a NavMeshBoundsVolume to your level and scale it to cover the roamable area. • Press P to confirm the green nav area is visible (indicating navigable space).

2. Create AI Character:
• Create a Blueprint character (e.g., BP_AIEnemy) with a skeletal mesh and AIController class. • Create an AI Controller Blueprint (e.g., BP_AIController) and assign it to the character.

3. Enable AI Perception:
• In BP_AIController, add an AIPerception component. • Configure a Sight sense (set detection range, lose sight range, peripheral vision angle). • Bind OnPerceptionUpdated to update a blackboard value (e.g., CanSeePlayer and PlayerActor).

Set Up Blackboard:
Create a Blackboard with the following keys:
• TargetLocation (Vector) • PlayerActor (Object) • CanSeePlayer (Bool)

Create Behavior Tree (BT_AI)
Custom Task: Find Random Location
• Create a new BTTask_BlueprintBase to get a random reachable point using: • UNavigationSystemV1::GetRandomReachablePointInRadius() • Set the result to the TargetLocation blackboard key.

Test the AI
• Add a player character to the level. • Place the AI enemy in the map and assign its controller and behavior tree. • Press Play: the AI should roam when the player is far and chase the player when within sight.

## OUTPUT

<img width="1041" height="712" alt="image" src="https://github.com/user-attachments/assets/ccb67050-1308-4acd-b85f-200ee23d323f" />
<img width="981" height="422" alt="image" src="https://github.com/user-attachments/assets/07040ed3-9289-42c2-a6f0-1cde5b7f6771" />
<img width="1016" height="382" alt="image" src="https://github.com/user-attachments/assets/7b7b041d-0e5f-4e76-beb9-768a6dc2ce4e" />

## Result

The AI character roams randomly within a defined area. When the player enters its sight range, the AI stops roaming and begins to chase the player until the player is out of sight, after which it resumes roaming.
