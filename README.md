## Обработка текста ##
Data.cs:
```c#
public class Data
    {
        internal string txt;
        internal string fileName;

        public void loadConfig()
        {
            try {
                using (
                    StreamReader sr =
                    new StreamReader("config.txt"))
                {
                    fileName = sr.ReadLine();
                }
            } catch (IOException ex)
            {
              
            }
        }
        public void readFromFile()
        {
            using (StreamReader sr
                = new StreamReader(fileName))
            { 
                txt = sr.ReadToEnd();
            }
        }

        public void saveConfig()
        {
            using (
                StreamWriter sw
                = new StreamWriter("config.txt"))
            {
                sw.WriteLine(fileName);
            }
        }
    }
```
