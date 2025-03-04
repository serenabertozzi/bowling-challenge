# Bowling Challenge

User Stories

```
As a bowling player,
So that I can start my match,
I want to be able to record a frame with two rolls.

As a bowling player,
So that I can record points,
I want to be able to record points when I score an open frame.

As a bowling player,
So that I can record points,
I want to be able to record points when I score a spare frame.

As a bowling player,
So that I can record points,
I want to be able to record points when I score a strike.

As a bowling player,
So that I can recieve a correct number of points,
I want to be able to record bonus points when scoring an open frame or a strike.

As a bowling player,
So that I can end my game,
I want to be able to throw a correct number of rolls for my last turn.

As a bowling player,
So that I can end my game and get a fair scoring,
I want to be able to record all the points of the last round.
```

# DOMAIN MODELING

![Installation](bowling.drawio.svg)

# APPROACH

- I created a Frame class, which accepts three rolls, and can be determined to be Open, Spare or Strike.
- Bowling class is the main one, and has the responsability to store all the frames of a match and to calculate score and bonuses.
- At last, I created a CLI with "readline-sync".

# RULES

### Strikes

The player has a strike if he knocks down all 10 pins with the first roll in a frame. The frame ends immediately (since there are no pins left for a second roll). The bonus for that frame is the number of pins knocked down by the next two rolls. That would be the next frame, unless the player rolls another strike.

### Spares

The player has a spare if the knocks down all 10 pins with the two rolls of a frame. The bonus for that frame is the number of pins knocked down by the next roll (first roll of next frame).

### 10th frame

If the player rolls a strike or spare in the 10th frame they can roll the additional balls for the bonus. But they can never roll more than 3 balls in the 10th frame. The additional rolls only count for the bonus not for the regular frame count.

    10, 10, 10 in the 10th frame gives 30 points (10 points for the regular first strike and 20 points for the bonus).
    1, 9, 10 in the 10th frame gives 20 points (10 points for the regular spare and 10 points for the bonus).

### Gutter Game

A Gutter Game is when the player never hits a pin (20 zero scores).

### Perfect Game

A Perfect Game is when the player rolls 12 strikes (10 regular strikes and 2 strikes for the bonus in the 10th frame). The Perfect Game scores 300 points.
