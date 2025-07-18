Hello World!
This project is in MAUI Blazor Hybrid. It's a handy CRUD GridView that is portable, independent and easy to use. You only need this example line:
<EbiGrid Rows="Varzesh_Karan" Update="(IList Updated) => Update(Updated)" Headers="Headers" />
where "Varzesh_Karan" is a List of people with this defenition:
    List<Person> Varzesh_Karan = new List<Person>();
    public class Person
    {
        public int ID { get; set; }
        public string First_Name { get; set; } = "";
        public string Last_Name { get; set; } = "";
        public string Car { get; set; } = "";
        public int Age { get; set; }
        public int Height { get; set; }
        public double Salary { get; set; }
    }
"Headers" is a Dictionary which you set the column titles of the table:
    Dictionary<string, string> Headers = new Dictionary<string, string>();
    Headers["ID"] = "ردیف";
    Headers["First_Name"] = "نام کوچک";
    Headers["Last_Name"] = "فامیلی";
    Headers["Car"] = "خودرو";
    Headers["Age"] = "سن";
    Headers["Height"] = "قد";
    Headers["Salary"] = "درآمد";
You need a method in your parent page, named, in this example, "Update". You get the updated list by CRUD in the child razor page.
    void Update(object Updated)
    {
        Varzesh_Karan = (List<Person>)Updated;
        // Remaining code for updating your database. For example EntityFramework.
    }
    
