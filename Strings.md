# 📌 C++ String STL Cheatsheet

This guide covers everything you need to **recall, revise, and reuse** about `std::string` in interviews, contests, or coding rounds.

---

## 🔤 Basic Functions

| Function                   | Usage                            | Example             |
| -------------------------- | -------------------------------- | ------------------- |
| `s.size()` or `s.length()` | Get length                       | `s.length()` → `5`  |
| `s[i]`                     | Access char at index             | `s[2]`              |
| `s.at(i)`                  | Safe access with bounds checking | `s.at(2)`           |
| `s.empty()`                | Check if empty                   | `if(s.empty())`     |
| `s.clear()`                | Make string empty                | `s.clear()`         |
| `s.front()` / `s.back()`   | First / Last char                | `s.front()` → `'a'` |

---

## 🔁 Iteration

```cpp
for(char c : s) cout << c;
for(int i = 0; i < s.length(); i++) cout << s[i];
```

---

## ➕ Modification

| Operation | Code                        | Description      |
| --------- | --------------------------- | ---------------- |
| Append    | `s += "xyz";`               | Add to end       |
| Push back | `s.push_back('c');`         | Add 1 char       |
| Pop back  | `s.pop_back();`             | Remove last char |
| Insert    | `s.insert(pos, str);`       | Add substring    |
| Erase     | `s.erase(pos, len);`        | Remove portion   |
| Replace   | `s.replace(pos, len, str);` | Replace portion  |

---

## 🔍 Search

| Function             | Purpose                  | Example                         |
| -------------------- | ------------------------ | ------------------------------- |
| `s.find("abc")`      | First occurrence         | Returns index or `string::npos` |
| `s.rfind("abc")`     | Last occurrence          |                                 |
| `s.substr(pos, len)` | Substring                | `s.substr(2, 3)`                |
| `s.compare(str)`     | Lexicographic comparison | `== 0` if equal                 |

---


## 📐 Conversion & Utilities

| Operation                      | Code                                                                          | Notes                             |
| ------------------------------ | ----------------------------------------------------------------------------- | --------------------------------- |
| Char to int                    | `ch - '0'`                                                                    | Only valid if `isdigit(ch)`       |
| Int to char                    | `'0' + x`                                                                     | For 0 ≤ x ≤ 9                     |
| String to int                  | `stoi(s)`                                                                     | Use `<string>`                    |
| Int to string                  | `to_string(x)`                                                                | Use `<string>`                    |
| Check if digit                 | `isdigit(ch)`                                                                 | True if `ch` is 0–9               |
| Check if alphabet              | `isalpha(ch)`                                                                 | True if `ch` is A–Z or a–z        |
| Check if alphanumeric          | `isalnum(ch)`                                                                 | True if `ch` is letter or digit   |
| Check if lowercase             | `islower(ch)`                                                                 | True if `ch` is lowercase         |
| Check if uppercase             | `isupper(ch)`                                                                 | True if `ch` is uppercase         |
| Check if whitespace            | `isspace(ch)`                                                                 | Spaces, tabs, newlines            |
| Convert to lowercase           | `tolower(ch)`                                                                 | Use with `for(char &c : s)`       |
| Convert to uppercase           | `toupper(ch)`                                                                 | Use with `for(char &c : s)`       |
| ASCII value of char            | `int(ch)`                                                                     | Useful for comparisons            |
| Char from ASCII                | `char(ascii_val)`                                                             | Reverse of above                  |
| Remove leading/trailing spaces | `s.erase(s.find_last_not_of(" ") + 1); s.erase(0, s.find_first_not_of(" "));` | Manual trimming                   |
| Check if all digits            | `all_of(s.begin(), s.end(), ::isdigit)`                                       | Entire string is numeric          |
| Check if all letters           | `all_of(s.begin(), s.end(), ::isalpha)`                                       | Entire string is alphabetic       |
| Count specific char            | `count(s.begin(), s.end(), 'x')`                                              | Counts how many times 'x' appears |
| Convert entire string to lower | `transform(s.begin(), s.end(), s.begin(), ::tolower);`                        | Requires `<algorithm>`            |
| Convert entire string to upper | `transform(s.begin(), s.end(), s.begin(), ::toupper);`                        | Requires `<algorithm>`            |


---

## 🧠 Tips & Gotchas

* `s.find(...) == string::npos` → Not found
* Always check bounds before `s[i]`
* Use `s.reserve()` if you're building a large string
* Use `stringstream` if frequent conversions are involved

---

## 🔁 Common Interview Tricks

* ✅ Check palindrome: `s == string(s.rbegin(), s.rend())`
* ✅ Reverse string: `reverse(s.begin(), s.end())`
* ✅ Frequency count:

```cpp
vector<int> freq(26, 0);
for(char c : s) freq[c - 'a']++;
```

---

## 📚 Practice Questions

* Reverse Words in a String
* Valid Palindrome with at most 1 removal
* Longest Substring Without Repeating Characters
* Minimum Window Substring

---

Feel free to add edge cases, custom templates, or your own hacks to this list!
