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



```C#
    string q = comboBox1.Text;
    Regex r = new Regex(q);
    Match m = r.Match(data.txt);
    if (m.Success)
            {
                richTextBox2.Text += "Найдено: " + m.Value;

                richTextBox1.SelectionBackColor = Color.White;
                richTextBox1.SelectionStart = m.Index;
                richTextBox1.SelectionLength = m.Value.Length;
                richTextBox1.SelectionBackColor = Color.Yellow;
                richTextBox1.ScrollToCaret();
            }
```

