# Extract-Emails
Write a program to extract all email addresses from a given text. The text comes at the only input line. Print the emails on the console, each at a separate line. Emails are considered to be in format &lt;user>@&lt;host>.


using System;
using System.Text.RegularExpressions;

class Extract1
{
    static void Main()
    {
        string input = Console.ReadLine();
        string pattern = @"(?<=\s|^)([a-z0-9]+(?:[_.-][a-z0-9]+)*@[a-z]+\-?[a-z]+(?:\.[a-z]+)+)\b";

        Regex rgx = new Regex(pattern);
        MatchCollection mts = rgx.Matches(input);

        foreach (Match email in mts)
        {
            Console.WriteLine(email.Groups[0]);
        }
    }
}

