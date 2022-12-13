use zen

db.createCollection("tasks,topic,users,codekatta,attendace,mentors,company_drives")


Find all the topics and tasks which are thought in the month of October

db.tasks.Find({month:"october"})
db.topics.Find({month:"october"})

Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020

db.company_drives.find({date:{$gte:“15 oct-2020lt:“31-oct-2020”}})

Find all the company drives and students who are appeared for the placement.

db.company_drives.find(placement:{$exists:true}},_id:0,students:1)

Find the number of problems solved by the user in codekata

db.codekatta.find({solved:{$exists:true}},_id:0,students:1)

Find all the mentors with who has the mentee's count more than 15

db.mentor.find({mentee:{$gt:15}},_id:0,name:1)

Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020

db.users.find({$and:[attendance:{$exists:true},tasks:{$gte:“15 oct-2020lt:“31-oct-2020”}]})
