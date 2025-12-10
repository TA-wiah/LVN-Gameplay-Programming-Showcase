# 08 Third Person Movement : Ladder Climbing

Welcome to the Ladder Climbing section of the LVN Gameplay Programming Showcase series.

Building on the [**07 Gliding Module**](https://github.com/LukkasVN/LVN-Gameplay-Programming-Showcase/tree/main/07_ThirdPersonMovement_Gliding), this entry introduces a prototype ladder climbing mechanic that lets the player attach to ladders, climb up or down, and exit smoothly at the top or bottom.  
The system is designed to remain modular, readable and almost fully inspector‑driven, while integrating with an existing locomotion setup.

<h2 align="center">Overview</h2>

<p align="center">
  <img src="https://github.com/user-attachments/assets/6e346996-dd81-493d-8fba-00bf590a3284" width="600px" />
</p>

> IMPORTANT NOTES:
>> 1. The ladder is only accessible when the player is close enough, and currently there is no climbing‑down adjustment system when approaching from the top.
>> 
>> 2. A specific setup of a Ladder GameObject/Prefab (Unity) or Actor/Blueprint (Unreal) is required in order to use the ladder climbing behaviour correctly.
>>    
>> 3. The rare teleporting behaviour when climbing up occurs because the animation is non‑rooted. Attempts to correct this with animation blending and mesh adjustments can only partially mask the issue.

This mechanic uses standard ladder colliders and Mixamo climbing animations adjusted to fit the gameplay context.  
Unity allows flexible animation blending through the Animator, while Unreal uses a more rigid but stable setup.  
Once the player interacts with a ladder, movement transitions into a controlled climb state with tweakable behaviour parameters.

<h3>Key features include:</h3>

- Player can attach to ladders from either side, with orientation automatically resolved  
- Vertical input drives climb speed up or down  
- Ladder offset and rotation fully adjustable via inspector variables  
- Clean exit handling at both the bottom and top of ladders  
- Camera target can be swapped during exit for smoother cinematic transitions
- Mesh/armature handling ensures animations stay visually locked during climb and exit  
- Supports both Unity C# and Unreal C++ implementations 

---

> NOTE : Climbing animations used come from **Mixamo** and were slightly adjusted to fit gameplay and visual needs.  

> Extra Note: To avoid controller bumps during teleport exits, the CharacterController is disabled briefly or `Warp` is used when available. This ensures smooth snapping to exit points without jitter.
