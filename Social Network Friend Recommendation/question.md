## Social Network Friend Recommendation

Problem Statement

Develop a friend recommendation system for a social network where each user has a list of friends. The system should support the following functionalities:

- Add User: Register a new user with a unique ID.
- Add Friendship: Establish a friendship between two users.
- Friend Recommendations: Recommend friends to a user based on mutual connections (friends of friends) who are not already directly connected.
- View Friends: Display all direct friends of a user.
  
The system should effectively use graph theory concepts, with users represented as nodes and friendships as edges. Friend recommendations are based on identifying users two hops away in the graph.

Input Format

The input consists of a series of operations that modify or query the social network.

Operations:

- Add User: addUser(user_id)
- Add Friendship: addFriendship(user_id1, user_id2)
- Friend Recommendations: getFriendRecommendations(user_id)
- View Friends: viewFriends(user_id)
  
Example Input:<br>

addUser(1)<br>
addUser(2)<br>
addUser(3)<br>
addFriendship(1, 2)<br>
addFriendship(2, 3)<br>
getFriendRecommendations(1)<br>
viewFriends(1)<br>

Output Format<br>

The output depends on the operation performed.

- Add User: Confirmation message like "User 1 added."
- Add Friendship: Confirmation message like "Friendship established between 1 and 2."
- Friend Recommendations: A list of recommended user IDs.
- View Friends: A list of direct friends.
  
Example Output:<br>

"User 1 added."<br>
"User 2 added."<br>
"User 3 added."<br>
"Friendship established between 1 and 2."<br>
"Friendship established between 2 and 3."<br>
Friend Recommendations for 1: [3]<br>
Friends of 1: [2]<br>

Concepts Used

- Graphs: Users are nodes, friendships are edges.
- BFS (Breadth-First Search): Used to find all friends at a distance of two hops (friends of friends).
- Hash Maps: Used to store user friendships efficiently.
  
Algorithm<br>

Add User:
- Create a new entry in the adjacency list for the user with an empty list of friends.

Add Friendship:
- Add each user to the other's adjacency list.

Friend Recommendations:
- Use BFS starting from the given user to find friends of friends.
- Filter out users who are already direct friends or the user themselves.
- Return the remaining users sorted by the number of mutual friends (optional for ranking).
  
View Friends:
- Return the adjacency list for the given user.
  
Example Walkthrough<br>

Input Sequence:<br>

addUser(1)<br>
addUser(2)<br>
addUser(3)<br>
addFriendship(1, 2)<br>
addFriendship(2, 3)<br>
getFriendRecommendations(1)<br>
viewFriends(1)<br>

Execution:<br>

1) User 1, 2, and 3 are added.<br>
2) Friendships are established: 1 ↔ 2 and 2 ↔ 3.<br>
3) getFriendRecommendations(1) performs BFS:<br>
- Friends of 1: [2]<br>
- Friends of 2 (excluding 1): [3]<br>
- Recommend 3 to 1.<br>
4) viewFriends(1) returns [2].<br>

Output:<br>

User 1 added.<br>
User 2 added.<br>
User 3 added.<br>
Friendship established between 1 and 2.<br>
Friendship established between 2 and 3.<br>
Friend Recommendations for 1: [3]<br>
Friends of 1: [2]<br>

Constraints:<br>

- 1 ≤ Number of Users ≤ 10,000<br>
- 1 ≤ Number of Friendships ≤ 100,000<br>
- User IDs are unique integers.<br>
- Friend recommendations should be optimized for performance.<br>
