## Rogue A.I.

Your mission: pilot a robot through a perilous, ever-changing labyrinth. But you're not at the controls, you're in its mind. Every command you issue, every piece of data you feed its core AI, shapes its understanding and actions. Can you master the art of subtle suggestion, anticipate its quirks, and outwit its limitations to guide it through the digital unknown? In Rogue A.I., your intelligence is its only hope.

---

### Game Breakdown: Rogue A.I.

**Implementation**
* The game implements a procedurally generated world with the robot and enemies.
* A real LLM running locally on the user's machine (not an emulation).
  * The LLM will NOT be told it is in a game.
  * What the game tells the LLM is what the LLM will see as the real-world.
* Game UI
  * Markdown based chat
  * Text editor to view/modify the context
  * Image from the robot's camera

**Core Concept:**
* A unique roguelike where the player, a hacker, guides a robot through a procedurally generated maze.
* **The central mechanic revolves around indirect control:** players communicate with the robot's in-game brain, which is a real Large Language Model (LLM) running locally on the player's system.
* The game incorporates emerging real-world skills
  - Prompt engineering (Markdown based chat interface)
  - Context management (User can edit the context manually in a text editor)
  - Meta-prompting (to better understand how the LLM is working)
  - Dealing with real LLM limitations

**Game Loop:**
* (Optional) Player edits the context in a simple text editor.
* Player enters prompt/instructions for the robot.
* The LLM (Phi-3 or any other smaller model) processes
    * Input
      * Instructions that it is a robot in a maze + other basics for it to work in the game world
      * The context
      * The player prompt
      * Visible world state
    * Output
      * Tool calls (same 
        *(Note: The robot's LLM tools are distinct from tools a general-purpose LLM might use, such as real-world web search. All robot actions and perceptions occur strictly within the game's simulated environment.)*
      * Updated context
* Game world updated
* Display updated

**Player Interaction & Control:**
* **Indirect Control via Text Prompts:** Players issue commands (e.g., "go north," "pick up item") as text inputs.
* **Imperfect LLM Brain:** The robot's brain is a smaller, genuine LLM, leading to natural imperfections, misinterpretations, and context decay.  There is nothing added to create these imperfections, they happen because this is a real LLM and constrained by the users system.
* **Context Management:**
    * Information automatically drops from the LLM's working memory over time or with new data.
    * Players can manually edit the robot's context information (acting as an "initial prompt") to influence its core understanding and behavior.
    * The robot can also update its own context.
    * **Conflict Resolution:** A "last one wins" rule applies to context updates, requiring players to strategically manage and curate the LLM's active memory.
* **"Meta-Prompting":** Players can use a turn to issue a "meta-prompt" to the LLM, asking it to describe its internal state or reasoning to gain insight into its behavior. This is essentially debugging the robot's mind.

**Robot Feedback & Environment:**
* **First-Person Visual Feed:** A grainy, monochrome snapshot from the robot's camera, updating one "square" at a time as it moves. This limited visual information creates tension and requires strategic interpretation.
* **Procedurally Generated Maze:** Each run presents a new, dangerous, multi-level environment.
* **Real-time vs. Turn-based:** The MVP will offer a toggle between turn-based play (allowing careful prompt engineering) and real-time play (demanding quick reflexes and decisions).

**Roguelike Elements & Progression:**
* **Permadeath:** Death is frequent, but each failed run provides valuable lessons about managing the unpredictable AI.
* **Scavenging & Crafting:** Players can find parts and discover new equipment to craft tools and improve the robot's chances of survival.
* **Robot Upgrades:** Improvements can enhance the robot's capabilities and potentially its understanding or processing.
* **Run Scoring:** Even without escaping, runs are scored by the total treasure value collected, allowing for comparison and meta-progression between attempts.

**Known and Accepted Challenges**
* Local LLM execution can cause each turn to take a large amount of time.
* Complexity & Niche Appeal
* Frustration vs. Fun: Getting the LLM to do what you want is the 'fun', if you find it frustrating, then this is not the game for you.
"Last One Wins" Context Resolution: Yes, this can cause loss of information if you don't watch out for it.  This is part of the challenge.
