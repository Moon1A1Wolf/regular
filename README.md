            #region 1. Сheck mail

            Console.WriteLine("Input your e-mail: ");
            string userMail = Console.ReadLine();

            string regular = @"^\w{1,20}@\w{1,20}\.\w{2,15}$";

            Regex regex = new Regex(regular);
            Match match = regex.Match(userMail);

            if (match.Success)
                Console.WriteLine("Your e-mail: " + match.Value + '\n');
            else { Console.WriteLine("You don't input e-mail!\n"); }

            #endregion


            #region 2. Find time ЧЧ:MM:CC

            string text = "12:15:00 ejkvnk 34:69:32  09;34;90 njn10:10:10ev 21:25:30";
            regular = @"\b([0-1][0-9]|[2][0-3]):[0-5][0-9]:[0-5][0-9]\b";

            regex = new Regex(regular);
            MatchCollection matchCollection = regex.Matches(text);

            for (int i = 0; i < matchCollection.Count; i++)
            {
                Console.WriteLine(matchCollection[i].Value);
            }
            Console.WriteLine();

            #endregion


            #region 3. Find date ДД:MM:ГГГГ

            text = "15.12.2005 57.34.2003 sdf23.10.2030 4.5.2006 29.02.2024 29.02.2023";
            regular = @"\b(0?[1-9]|[12]\d|3[01])\.(0?[1-9]|1[0-2])\.\d{4}\b";
            regex = new Regex(regular);
            matchCollection = regex.Matches(text);

            for (int i = 0; i < matchCollection.Count; i++)
            {
                Console.WriteLine(matchCollection[i].Value);
            }
            Console.WriteLine();

            #endregion
