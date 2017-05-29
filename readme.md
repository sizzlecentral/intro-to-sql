[See assignment in Alexa.](https://alexa.bitmaker.co/cohorts/72/assignments/2244/latest)

# ----- Answers ----- #


1.  Find all the robots from The Hitchhiker's Guide to the Galaxy.

    SELECT name FROM robots WHERE source='The Hitchhiker''s Guide to the Galaxy';
    => Marvin, Deep Thought

2.  Find the robot with an "anxious" personality.

    SELECT name FROM robots WHERE personality='anxious';
    => C3PO

3.  Find all recipes that are nut free.

    SELECT name FROM recipes WHERE nut_free='t';
    => Butternut Squash Bake, Vegetarian Bibimbap,
      French Veggie Loaf, Quinoa and Black Beans,
      Juicy Roasted Chicken, Garlic Green Beans,
      Stout Slow Cooker Corned Beef and Veggies

4.  Count the number of recipes that are gluten free but not vegetarian.

    SELECT COUNT(gluten_free) FROM recipes WHERE NOT vegetarian;
    => 2

5.  Find the animal with the most legs.

    SELECT name FROM animals WHERE number_of_legs=(SELECT MAX(number_of_legs) FROM animals);
    => Octopus

6.  Find the board game that takes the least amount of time to play.

    SELECT name FROM board_games WHERE mins_to_play=(SELECT MIN(mins_to_play) from board_games);
    => Sushi Go, Quixo

7.  Find the recipe that takes the most time to prepare.

    SELECT name FROM recipes WHERE minutes_required=(SELECT MAX(minutes_required) FROM recipes);
    => Stout Slow Cooker Corned Beef and Veggies

8.  Find all the robots whose name starts with the letter M.

    SELECT * FROM robots WHERE name LIKE 'M%';
    => Marvin, Mr. Butlertron

9.  Count the number of board games that can be played by 8 people.

    SELECT name FROM board_games WHERE min_players <= 8 AND max_players >= 8;
    => Arkham Horror, Cards Against Humanity, Game of Things

10.  Find all animals that are swimming and egg-laying.

    SELECT name FROM animals WHERE swimming='t' AND egg_laying='t';
    => Octopus, Duck

11.  Find all animals that are swimming and egg-laying but not flying.

    SELECT name FROM animals WHERE swimming='t' AND egg_laying='t' AND flying='f';
    => Octopus

12.  Find the board game that supports the largest number of people.

    SELECT name FROM board_games WHERE max_players=(SELECT MAX(max_players) FROM board_games);
    => Cards Against Humanity
