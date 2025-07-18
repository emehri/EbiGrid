Hello World!<br>
This project is in MAUI Blazor Hybrid. 
It's a handy CRUD GridView that is portable, independent and easy to use. You only need this example line:<br>
<EbiGrid Rows="Varzesh_Karan" Update="(IList Updated) => Update(Updated)" Headers="Headers" /><br>
where "Varzesh_Karan" is a List of people with this defenition:<br>
    List<Person> Varzesh_Karan = new List<Person>();<br>
    public class Person<br>
    {<br>
        public int ID { get; set; }<br>
        public string First_Name { get; set; } = "";<br>
        public string Last_Name { get; set; } = "";<br>
        public string Car { get; set; } = "";<br>
        public int Age { get; set; }<br>
        public int Height { get; set; }<br>
        public double Salary { get; set; }<br>
    }<br>
"Headers" is a Dictionary which you set the column titles of the table:<br>
    Dictionary<string, string> Headers = new Dictionary<string, string>();<br>
    Headers["ID"] = "ردیف";<br>
    Headers["First_Name"] = "نام کوچک";<br>
    Headers["Last_Name"] = "فامیلی";<br>
    Headers["Car"] = "خودرو";<br>
    Headers["Age"] = "سن";<br>
    Headers["Height"] = "قد";<br>
    Headers["Salary"] = "درآمد";<br>
You need a method in your parent page, named, in this example, "Update". You get the updated list by CRUD in the child razor page.<br>
    void Update(object Updated)<br>
    {<br>
        Varzesh_Karan = (List<Person>)Updated;<br>
        // Remaining code for updating your database. For example EntityFramework.<br>
    }<br>
    
