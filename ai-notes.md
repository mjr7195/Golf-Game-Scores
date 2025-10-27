This document tracks the prompts, tools, and decisions made during the development of the Golf Scorecard application.

Tools Used:

    HTML

    Tailwind CSS (via CDN)

    Vanilla JavaScript

    Browser Local Storage (for game history and par values)

    Google Gemini

Key Prompts & Iterations

1. Initial Prompt

    Prompt: "Can you create a Golf score keeping game in html, css and javascript. Create a good wire frame first to show me if I like the design"

    Action:
        
        Created golf_wireframe.md to outline the structure.

    Created the first version of golf_scorecard.html which showed all 18 holes on one screen.

2. Suggestion: Hole-by-Hole View

    Prompt: "can you make it so all the scores don't show up at the same time and it is hole by hole. and allow the user to pick how many holes that are to play."

    Accepted? Yes.

    Why: The original design would have been very difficult to use on a mobile device (requiring a lot of horizontal scrolling). This change focused the user on the current task (entering scores for one hole) and made the layout responsive and clean.

    Changes:

        Refactored the UI from a single large table to a "screen-based" system (game-setup, scorecard-container).

        Added logic (currentHole, nextHole(), prevHole()) to navigate between holes.

        Added buttons to select 9 or 18 holes, storing the choice in numHoles.

3. Suggestion: Winner Screen & Local Storage

    Prompt: "let it finish after the last hole is completed and show the winner. store the game results all locally."

    Accepted? Yes.

    Why: This suggestion provides a clear "end" to the game and makes the app far more useful by giving it memory. The user gets to see who won, and the local storage feature lets them see see past games and winners.

    Changes:

        Added a new results-screen div.

        The "Next" button now changes to "Finish Game" on the last hole.

        Added finishGame() logic to calculate scores, find the winner(s), and display the results.

        Implemented saveGame() and loadAndDisplayHistory() functions using localStorage to store and retrieve past games.

        Added the "Game History" section to the setup screen.

Reflection:

    Accuracy: 
        Gemini was pretty accurate in what I asked of it. I only needed to refine it due to me not being specific after each prompt I sent. 

    Pitfalls:
        Much like in accuracy the only pitfalls I went through were due to the prompts I sent. But it helped me improve the overall design after each each version until I got what I wanted. 

    Verified Outputs:
        I used Visual Studio Code to build HTML and CSS to build the application. There is a preview extension that lets you view the code that you just made. This was very helpful when creating the score keeping application. 



