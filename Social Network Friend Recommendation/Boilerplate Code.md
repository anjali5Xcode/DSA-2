## JAVA

```java
import java.util.*;

class SocialNetwork {
    private Map<Integer, Set<Integer>> friends = new HashMap<>();

    public void addUser(int userId) {
        friends.putIfAbsent(userId, new HashSet<>());
        System.out.println("User " + userId + " added.");
    }

    public void addFriendship(int user1, int user2) {
        friends.get(user1).add(user2);
        friends.get(user2).add(user1);
        System.out.println("Friendship established between " + user1 + " and " + user2 + ".");
    }

    public List<Integer> getFriendRecommendations(int userId) {
        Set<Integer> visited = new HashSet<>();
        for (int friend : friends.getOrDefault(userId, Collections.emptySet())) {
            for (int potential : friends.getOrDefault(friend, Collections.emptySet())) {
                if (potential != userId && !friends.get(userId).contains(potential)) {
                    visited.add(potential);
                }
            }
        }
        return new ArrayList<>(visited);
    }

    public void viewFriends(int userId) {
        System.out.println("Friends of " + userId + ": " + friends.getOrDefault(userId, Collections.emptySet()));
    }

    public static void main(String[] args) {
        SocialNetwork sn = new SocialNetwork();
        sn.addUser(1);
        sn.addUser(2);
        sn.addUser(3);
        sn.addFriendship(1, 2);
        sn.addFriendship(2, 3);
        System.out.println("Friend Recommendations for 1: " + sn.getFriendRecommendations(1));
        sn.viewFriends(1);
    }
}
```

## C++
```C++
#include <iostream>
#include <unordered_map>
#include <unordered_set>
#include <vector>
#include <queue>

class SocialNetwork {
    std::unordered_map<int, std::unordered_set<int>> friends;

public:
    void addUser(int user_id) {
        friends[user_id];  // Initializes an empty set for the user
        std::cout << "User " << user_id << " added.\n";
    }

    void addFriendship(int user1, int user2) {
        friends[user1].insert(user2);
        friends[user2].insert(user1);
        std::cout << "Friendship established between " << user1 << " and " << user2 << ".\n";
    }

    std::vector<int> getFriendRecommendations(int user_id) {
        std::unordered_set<int> visited;
        std::vector<int> recommendations;
        for (int friend_id : friends[user_id]) {
            for (int potential : friends[friend_id]) {
                if (potential != user_id && friends[user_id].find(potential) == friends[user_id].end()) {
                    visited.insert(potential);
                }
            }
        }
        recommendations.assign(visited.begin(), visited.end());
        return recommendations;
    }

    void viewFriends(int user_id) {
        std::cout << "Friends of " << user_id << ": ";
        for (int friend_id : friends[user_id]) {
            std::cout << friend_id << " ";
        }
        std::cout << "\n";
    }
};

int main() {
    SocialNetwork sn;
    sn.addUser(1);
    sn.addUser(2);
    sn.addUser(3);
    sn.addFriendship(1, 2);
    sn.addFriendship(2, 3);
    std::vector<int> recommendations = sn.getFriendRecommendations(1);
    std::cout << "Friend Recommendations for 1: ";
    for (int user : recommendations) {
        std::cout << user << " ";
    }
    std::cout << "\n";
    sn.viewFriends(1);
    return 0;
}
```
## Python
```python
class SocialNetwork:
    def __init__(self):
        self.friends = {}

    def add_user(self, user_id):
        self.friends.setdefault(user_id, set())
        print(f"User {user_id} added.")

    def add_friendship(self, user1, user2):
        self.friends[user1].add(user2)
        self.friends[user2].add(user1)
        print(f"Friendship established between {user1} and {user2}.")

    def get_friend_recommendations(self, user_id):
        visited = set()
        for friend in self.friends.get(user_id, []):
            for potential in self.friends.get(friend, []):
                if potential != user_id and potential not in self.friends[user_id]:
                    visited.add(potential)
        return list(visited)

    def view_friends(self, user_id):
        print(f"Friends of {user_id}: {list(self.friends.get(user_id, []))}")

if __name__ == "__main__":
    sn = SocialNetwork()
    sn.add_user(1)
    sn.add_user(2)
    sn.add_user(3)
    sn.add_friendship(1, 2)
    sn.add_friendship(2, 3)
    print(f"Friend Recommendations for 1: {sn.get_friend_recommendations(1)}")
    sn.view_friends(1)
```
