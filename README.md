using System;
using Telegram.Bot;

namespace TelegramBotDemo
{
    class Program
    {
        private static TelegramBotClient client = null;
        static void Main(string[] args)
        {
            Console.WriteLine("haidar hatam ali");
            client = new TelegramBotClient("5045907787:AAE1pcDrQMzzaoXWc0wWM9zi08i6_8emZ2s");
            client.OnMessage += Client_OnMessage;
            client.StartReceiving();
            Console.ReadLine();
        }

        private static void Client_OnMessage(object sender, Telegram.Bot.Args.MessageEventArgs e)
        {
            Console.WriteLine($"Botdan kelgan xabar:{e.Message.Text}");
            if (e.Message.Text.ToLower().Contains("hi"))
                client.SendTextMessageAsync(e.Message.Chat.Id, "hello");
                else (client.SendTextMessageAsync(e.Message.Chat.Id, "please wait the admin");
        }
    }
}
