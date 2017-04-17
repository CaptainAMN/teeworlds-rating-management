# teeworlds-rating-management
Design documents, other text files, no code

Design document is as follows:


*Our goal:


To create a ranking system with a ladder, where we can see which clan is the strongest. Random teams do not have the benefit of a place in the ladder. It is reserved for long term teams, a.k.a clans. A clan's ranking actually is based on individual player ratings. The total power of a clan comes from it's players. The players individually receive their ranking either by clanwars, or by participating in "official" capgames. 


* The method:

Every data is collected centrally in a database. To create a new user, you have to register on the webpage. You create username and password, and to connect to the data base when u play, you have to log in from the client.

The result of a little discussion is that we follow the same path as Teerace login system with API token edited in the settings CFG of the player. This means that every player has to authentificate before he is able to receive his rating in the database! (Does someone know if we can add a "login successful" displayed to the player by the server, to confirm the login?)

(http://race.teesites.net/getstarted/)

Every line up creates a different total rating for the clan, because we base the clan rating on the combined player rating. Depending on which players you face in a clan war, you get different points in case u win or draw the game. In reality, the difference in points between different clan line ups will usually not be very big, because only exceptionally good or bad players can affect the total clan rating by a big number. But this is still very possible, because these players absolutely exist and affect games positively or negatively.



*The rating system:


It is based off of ingame score.


For every win: in a team, you get base points. If you perform well or bad in relation to average team score, your base score will receive either extra points or get a substraction, and your personal rating will be either boosted or will suffer.


For every loss: you do not receive points, losing is tough.  It's all about the teamplay. The player(s) that caused the loss should get their rating taken down severely. 


The ranking system in more detail:

Everyone gets the same points basically per win, but get better ratings if their scores are exceptionally high or get a really severe punishment if their score is really low.

Proposed is that the closer the top scorer is to a factor of 2 (or grerater) of the team's average points ingame, the more extra points you can collect for your individual rating.


The closer u are to half of the average score, the more severe the punishment for your rating. If you are even below half of the teams average, your rating should suffer quite a bit from it (especially if you lose the game!)

Game modes are: 
ctf3 (3on3)
ctf2 (4on4,5on5,6on6)
ctf5 (5on5, 6on6, 7on7,8on8)
ctf_tantum (4on4)

+++++Special rules for clanwars:+++++

Since all of this is based on ELO, we have to discourage repetitive maps and small teams. We have two options here. Seperate ELO rankings per map, what would be more accurate, but lack diversity. Secondly, to add a coefficient for undesired maps, so that your ranking does not get the "full" ranking boost. Else, a team of 3 players could single handedly push the ranking simply by only playing ctf3. Ergo, the points you potentially earn will be multiplied by a coefficient that is proprietary to the defined map. 

Alas, ctf2 has the coefficient "1".
ctf3 has "0.5"
ctf5 has "1.1"
ctf_tantum has "1".

=This is an unfinished draft=




