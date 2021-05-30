# nodeJs-developer-assignment


Tables - user,gameResults, gamesData, leaderBoard

Users can register using phone number and password. Users can login through phone
number and password and get access token. Each user will be having a user-profile which
stores basic information of the user. (Name, Age, Location, Email Id, phoneNumber). There
will be 3 games, each with a unique id. There will be a leaderboard which ranks users based
on certain criterias (wins, points scored) for each game. There will be an admin who can
post the result of a game between two players.
Features from the server:
• User need to be authenticated (JWT/OAuth) when using the APIs
• User can update his information except phone number
• Users can get a list of games.
• An Admin will post the result of a game between two users. The payload for the
result will be - gameId, u1Id, u2Id, scoreU1, scoreU2, win (boolean wrt u1, if true
then u1 wins else u2 wins).
• Users cannot post game results
• Based on results, an aggregated value will be used to get total points for users for
each game.
• Users can see aggregated scores of each user for each game (leaderboard).
• Example
o payload1 - {u1Id: 1, u2Id: 2, scoreU1: 30, scoreU2: 40, win: false, gameId:1}
o Payload2 - {u1Id: 2, u2Id: 3, scoreU1: 45, scoreU2: 40, win: true, gameId:1}
o Payload3 - {u1Id: 1, u2Id: 3, scoreU1: 45, scoreU2: 40, win: true, gameId:2}
• For game with gameId 1 leaderboard will be
o U2 -Rank 1, totalWins 2, totalPoints - 85
o U3 - Rank 3, totalWins 0, totalPoints - 40
o U1 - Rank 2, totalWins 0, totalPoints - 30
• For game with gameId 2 leaderboard will be
o U1 - Rank 1, totalWins 1, totalPoints - 45
o U3 - Rank 2, totalWins 0, totalPoints - 40
