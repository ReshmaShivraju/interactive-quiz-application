import random

print("======================================")
print("         CSE & ECE QUIZ SYSTEM        ")
print("======================================")

name = input("Enter your name: ")
print("\nWelcome", name, "🚀\n")

quiz = {

    "CSE": {

        "Data Structures": [

            {"q":"FIFO principle is used in?","o":["Stack","Queue","Tree","Graph"],"a":1},
            {"q":"LIFO principle is used in?","o":["Queue","Stack","Tree","Array"],"a":1},
            {"q":"Binary search requires?","o":["Sorted array","Unsorted array","Tree only","Graph only"],"a":0},
            {"q":"Worst case of linear search?","o":["O(1)","O(log n)","O(n)","O(n²)"],"a":2},
            {"q":"Stack overflow occurs when?","o":["Stack empty","Stack full","Queue full","Array sorted"],"a":1},
            {"q":"Queue insertion is called?","o":["Push","Insert","Enqueue","Add"],"a":2},
            {"q":"Recursion uses internally?","o":["Queue","Stack","Tree","Graph"],"a":1},
            {"q":"Graph consists of?","o":["Nodes & Edges","Arrays","Tables","Stacks"],"a":0},
            {"q":"Linked list stores elements in?","o":["Contiguous memory","Random memory","Nodes","Stack"],"a":2},
            {"q":"Binary tree maximum children?","o":["1","2","3","4"],"a":1},
            {"q":"Time complexity of binary search?","o":["O(n)","O(log n)","O(n²)","O(1)"],"a":1},
            {"q":"Which is non-linear DS?","o":["Array","Linked list","Tree","Queue"],"a":2},
            {"q":"Stack deletion is called?","o":["Push","Pop","Delete","Remove"],"a":1},
            {"q":"Queue deletion is called?","o":["Dequeue","Pop","Push","Remove"],"a":0},
            {"q":"Heap is based on?","o":["Binary Tree","Graph","Array","Queue"],"a":0},
            {"q":"DFS uses?","o":["Stack","Queue","Array","Graph"],"a":0},
            {"q":"BFS uses?","o":["Stack","Queue","Tree","Array"],"a":1},
            {"q":"Hashing is used for?","o":["Searching","Sorting","Deleting","Printing"],"a":0},
            {"q":"Linked list pointer stores?","o":["Data","Address","Index","Size"],"a":1},
            {"q":"Which DS is dynamic?","o":["Array","Linked list","Static array","Fixed table"],"a":1},
            {"q":"Circular queue avoids?","o":["Overflow","Underflow","Memory waste","Sorting"],"a":2},
            {"q":"Binary search tree left child?","o":["Smaller","Greater","Equal","Random"],"a":0},
            {"q":"Postfix evaluation uses?","o":["Stack","Queue","Tree","Graph"],"a":0},
            {"q":"Adjacency matrix represents?","o":["Graph","Tree","Queue","Stack"],"a":0},
            {"q":"Priority queue removes?","o":["Highest priority","Lowest priority","Random","Middle"],"a":0}
        ],

        "DBMS": [
            {"q":"SQL stands for?","o":["Structured Query Language","Simple Query","System Query","None"],"a":0},
            {"q":"Primary key must be?","o":["Unique","Null","Duplicate","Random"],"a":0},
            {"q":"Command to retrieve data?","o":["GET","SELECT","FETCH","SHOW"],"a":1},
            {"q":"Foreign key is used to?","o":["Link tables","Delete rows","Create DB","Sort data"],"a":0},
            {"q":"Normalization removes?","o":["Redundancy","Speed","Security","Index"],"a":0},
            {"q":"DELETE removes?","o":["Row","Table","Database","Column"],"a":0},
            {"q":"DBMS type?","o":["Relational","Binary","Static","Linear"],"a":0},
            {"q":"Index improves?","o":["Speed","Storage","Size","Error"],"a":0},
            {"q":"ER diagram represents?","o":["Entities","Loops","Stacks","Graphs"],"a":0},
            {"q":"Constraint ensures?","o":["Accuracy","Error","Crash","Delete"],"a":0},
            {"q":"DDL stands for?","o":["Data Definition Language","Data Delete Language","Direct Data Link","None"],"a":0},
            {"q":"DML stands for?","o":["Data Manipulation Language","Data Make Language","Delete Manipulation","None"],"a":0},
            {"q":"Candidate key is?","o":["Possible primary key","Duplicate key","Null key","Foreign key"],"a":0},
            {"q":"Tuple represents?","o":["Row","Column","Table","Database"],"a":0},
            {"q":"Attribute represents?","o":["Column","Row","Database","Query"],"a":0},
            {"q":"JOIN is used to?","o":["Combine tables","Delete tables","Create DB","Sort data"],"a":0},
            {"q":"WHERE clause filters?","o":["Rows","Columns","Tables","DB"],"a":0},
            {"q":"GROUP BY is used for?","o":["Aggregation","Deletion","Insertion","Sorting"],"a":0},
            {"q":"HAVING works with?","o":["GROUP BY","SELECT","DELETE","DROP"],"a":0},
            {"q":"ACID property ensures?","o":["Reliability","Speed","Size","Delete"],"a":0},
            {"q":"Transaction means?","o":["Unit of work","Delete","Insert","Query"],"a":0},
            {"q":"Deadlock is?","o":["Blocked state","Error","Crash","Delete"],"a":0},
            {"q":"Backup is used for?","o":["Recovery","Delete","Crash","Sorting"],"a":0},
            {"q":"View is?","o":["Virtual table","Physical table","Index","Key"],"a":0},
            {"q":"Schema defines?","o":["Structure","Data","Query","Delete"],"a":0}
        ],

        "Operating Systems": [],
        "Computer Networks": []
    },

    "ECE": {

        "Digital Electronics": [],
        "Signals and Systems": [],
        "Microprocessors": [],
        "Communication Systems": []

    }
}

# STREAM SELECTION
streams = list(quiz.keys())
for i, s in enumerate(streams,1):
    print(i, ".", s)

selected_stream = streams[int(input("Choose Stream: ")) - 1]

# SUBJECT SELECTION
subjects = list(quiz[selected_stream].keys())
for i, s in enumerate(subjects,1):
    print(i, ".", s)

selected_subject = subjects[int(input("Choose Subject: ")) - 1]

questions = quiz[selected_stream][selected_subject]

if len(questions) == 0:
    print("\nQuestions not added yet for this subject.")
else:
    random.shuffle(questions)
    score = 0

    for q in questions:
        print("\n" + q["q"])
        for i, opt in enumerate(q["o"],1):
            print(i, ".", opt)

        ans = int(input("Your answer (1-4): ")) - 1

        if ans == q["a"]:
            print("Correct ✅")
            score += 1
        else:
            print("Wrong ❌ Correct:", q["o"][q["a"]])

    percentage = (score/25)*100

    print("\n================================")
    print("RESULT")
    print("================================")
    print("Name:", name)
    print("Score:", score, "/25")
    print("Percentage:", percentage, "%")

