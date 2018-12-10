# Day 9: Marble Mania

You talk to the Elves while you wait for your navigation system to initialize. To pass the time, they introduce you to their favorite [marble](https://en.wikipedia.org/wiki/Marble_(toy)) game.

The Elves play this game by taking turns arranging the marbles in a **circle** according to very particular rules. The marbles are numbered starting with `0` and increasing by `1` until every marble has a number.

First, the marble numbered `0` is placed in the circle. At this point, while it contains only a single marble, it is still a circle: the marble is both clockwise from itself and counter-clockwise from itself. This marble is designated the **current marble**.

Then, each Elf takes a turn placing the l**owest-numbered remaining marble** into the circle between the marbles that are `1` and `2` marbles clockwise of the current marble. (When the circle is large enough, this means that there is one marble between the marble that was just placed and the current marble.) The marble that was just placed then becomes the **current marble**.

However, if the marble that is about to be placed has a number which is a multiple of `23`, **something entirely different happens**. First, the current player keeps the marble they would have placed, adding it to their **score**. In addition, the marble `7` marbles **counter-clockwise** from the current marble is **removed** from the circle and **also** added to the current player's score. The marble located immediately **clockwise** of the marble that was removed becomes the new **current marble**.

For example, suppose there are 9 players. After the marble with value `0` is placed in the middle, each player (shown in square brackets) takes a turn. The result of each of those turns would produce circles of marbles like this, where clockwise is to the right and the resulting current marble is in parentheses:

<pre>
[-] <strong>(0)</strong>
[1]  0 <strong>(1)</strong>
[2]  0 <strong>(2)</strong> 1
[3]  0  2  1 <strong>(3)</strong>
[4]  0 <strong>(4)</strong> 2  1  3
[5]  0  4  2 <strong>(5)</strong> 1  3
[6]  0  4  2  5  1 <strong>(6)</strong> 3
[7]  0  4  2  5  1  6  3 <strong>(7)</strong>
[8]  0 <strong>(8)</strong> 4  2  5  1  6  3  7
[9]  0  8  4 <strong>(9)</strong> 2  5  1  6  3  7
[1]  0  8  4  9  2<strong>(10)</strong> 5  1  6  3  7
[2]  0  8  4  9  2 10  5<strong>(11)</strong> 1  6  3  7
[3]  0  8  4  9  2 10  5 11  1<strong>(12)</strong> 6  3  7
[4]  0  8  4  9  2 10  5 11  1 12  6<strong>(13)</strong> 3  7
[5]  0  8  4  9  2 10  5 11  1 12  6 13  3<strong>(14)</strong> 7
[6]  0  8  4  9  2 10  5 11  1 12  6 13  3 14  7<strong>(15)</strong>
[7]  0<strong>(16)</strong> 8  4  9  2 10  5 11  1 12  6 13  3 14  7 15
[8]  0 16  8<strong>(17)</strong> 4  9  2 10  5 11  1 12  6 13  3 14  7 15
[9]  0 16  8 17  4<strong>(18)</strong> 9  2 10  5 11  1 12  6 13  3 14  7 15
[1]  0 16  8 17  4 18  9<strong>(19)</strong> 2 10  5 11  1 12  6 13  3 14  7 15
[2]  0 16  8 17  4 18  9 19  2<strong>(20)</strong>10  5 11  1 12  6 13  3 14  7 15
[3]  0 16  8 17  4 18  9 19  2 20 10<strong>(21)</strong> 5 11  1 12  6 13  3 14  7 15
[4]  0 16  8 17  4 18  9 19  2 20 10 21  5<strong>(22)</strong>11  1 12  6 13  3 14  7 15
[5]  0 16  8 17  4 18<strong>(19)</strong> 2 20 10 21  5 22 11  1 12  6 13  3 14  7 15
[6]  0 16  8 17  4 18 19  2<strong>(24)</strong>20 10 21  5 22 11  1 12  6 13  3 14  7 15
[7]  0 16  8 17  4 18 19  2 24 20<strong>(25)</strong>10 21  5 22 11  1 12  6 13  3 14  7 15
</pre>

The goal is to be the **player with the highest score** after the last marble is used up. Assuming the example above ends after the marble numbered `25`, the winning score is <code>23+9=<strong>32</strong></code> (because player 5 kept marble `23` and removed marble 9, while no other player got any points in this very short example game).

Here are a few more examples:

- `10` players; last marble is worth `1618` points: high score is <code><strong>8317</strong></code>
- `13` players; last marble is worth `7999` points: high score is <code><strong>146373</strong></code>
- `17` players; last marble is worth `1104` points: high score is <code><strong>2764</strong></code>
- `21` players; last marble is worth `6111` points: high score is <code><strong>54718</strong></code>
- `30` players; last marble is worth `5807` points: high score is <code><strong>37305</strong></code>

**What is the winning Elf's score?**