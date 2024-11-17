import random 
import telebot
from telebot.types import Message


bot = telebot.TeleBot("8161647641:AAHkDbSp5fQIASH7ghTKJ5R-WSjdbpuwfsQ")


@bot.message_handler(commands=['start'])
def cmd_Start(message: Message):
    bot.reply_to(message, 'Hello my friend! Im new bot to recycle the trash that people throwing away at streets and around the world (type /help for more)')




@bot.message_handler(commands=['cardboard'])
def cmd_cardboard(message: Message):
    bot.reply_to(message, 'Это картон, он выкидывается на улицах и в разных других местах')




@bot.message_handler(commands=['Recycler'])
def cmd_recycler(message: Message):
    bot.reply_to(message, 'У вас в городе есть переработка картона, пластика и разного друго мусора. Думаю вам нужно пройтись на улице, собрать мусор, и переработать чтобы сделать мир чище.')





@bot.message_handler(commands=['Fact'])
def cmd_fact(message: Message):
    Fact = random.randint(0,1)
    if Fact == 1:
        bot.reply_to(message, '• На производство 1 бутылки тратится такое же количество энергии, как на переработку 10 таких же изделий.')
    else:
        bot.reply_to(message, '• 27 тысяч деревьев ежегодно превращаются в туалетную бумагу. Этот продукт также может быть изготовлен из вторсырья.')




@bot.message_handler(commands=['help'])
def cmd_recycler(message: Message):
    bot.reply_to(message, 'Вот команды которые есть в боте - /Fact, /Recycler, /cardboard,')


bot.polling()
