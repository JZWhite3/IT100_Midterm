[Home](https://github.com/JZWhite3/IT100_Midterm/blob/main/README.md)
[Work Expirence](https://github.com/JZWhite3/IT100_Midterm/blob/main/WorkExperience.md)
[Education](https://github.com/JZWhite3/IT100_Midterm/blob/main/Education.md)
# Work Expireince and Projects
![luca-bravo-9l_326FISzk-unsplash](https://user-images.githubusercontent.com/123113593/226236986-5a69762c-d723-4dfb-bd89-cd81a53a1009.jpg)

## Electronic Lab Technician | Invention House LLC 
*Specializing in single-phase, 3-phase drives, and 400 Hz aviation motor drives.*      
- Support engineering activities such as design, test, modification, fabrication and assembly of prototype electromechanical systems, experimental design circuitry or specialized test equipment. Applications include analog, digital and power electronic systems.
- Independently work from schematics in Mentor Graphics and Altium, diagrams, written and verbal descriptions, layouts, and defined plans to perform modifications, testing, and trouble-shooting functions.
- Uses test, development, and diagnostic equipment, including, but not limited to, digital multimeters, oscilloscopes, current and voltage probes, waveform generators, spectrum analyzers, and specialized test apparatus.
- Work with lead engineers to develop product specific test fixtures and environments to meet military spec.

## Chief Executive Officer | Scout Team Technology LLC 
* Data collection solutions for construction, infrastructure, and project management companies *
- Founded the company with a focus in developing data collection solutions in order to assist construction companies in documentation of project lifecycles.
- Developed and managed client crm, company administrative and operational processes, and field project management.
- Oversee corporate operations and develop strategic plans of growth.
- Served as the public face of the company.
- Assured financial/budget stability.
- Developed a means to track metrics in order to report to company stakeholders.


## Projects 
### Student Report Main
```
namespace MidtermProject;
class Program
{
    static void Main(string[] args)
    {
        List<Student> studentList = new List<Student>();

        using (StreamReader reader = new StreamReader("student_data.csv")){
                
            int lineNum = 0;
            while (!reader.EndOfStream){

                string lineOFData = reader.ReadLine()!;
                lineNum += 1;

                string[] dataFromLine = lineOFData.Split(",");

                string firstName = dataFromLine[0];
                string lastName = dataFromLine[1];
                string major = dataFromLine[3];
                int creditHours = int.Parse(dataFromLine[2]);
                float score1 = float.Parse(dataFromLine[4]);
                float score2 = float.Parse(dataFromLine[5]);
                float score3 = float.Parse(dataFromLine[6]);
                    
                studentList.Add(new Student(firstName, lastName, major, creditHours, score1, score2, score3));
                    
            }
        }

        foreach(Student student in studentList){
            student.printStudentInfo();
            using StreamWriter fileWriter = new StreamWriter("report.txt");
            try{
                fileWriter.WriteLine("--------------Student Grade Report--------------");
                fileWriter.WriteLine("------------------------------------------------");
                fileWriter.WriteLine(student.printStudentInfo);
            
  
            }catch(Exception err){
                Console.WriteLine("Exception: "+ err.Message);
            }finally{
                if(fileWriter != null){
                    fileWriter.Close();
                }
            }
        }      
        Student testStudent = new Student("Truman", "Tiger", "Journalism", 87, 91.20f, 82.50f, 93.40f);
        testStudent.printStudentInfo();
        testStudent.addHours(10);
        testStudent.setFirstName("Tracy");
        testStudent.setLastName("Turtle");
        testStudent.setMajor("Comunications");
        testStudent.printStudentInfo();
    }
}
```
