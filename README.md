# SONIQ-Music-Bot
import os
from pyrogram import Client, filters

# Bot တည်ဆောက်ရန်အတွက် Telegram API Key များ (Environment Variables မှ ယူမည်)
API_ID = int(os.environ.get("API_ID", "0"))
API_HASH = os.environ.get("API_HASH", "")
BOT_TOKEN = os.environ.get("BOT_TOKEN", "")

# Pyrogram Client ဖြင့် Bot ကို စတင်ခြင်း
app = Client(
    "SONIQ_Music_Bot",
    api_id=API_ID,
    api_hash=API_HASH,
    bot_token=BOT_TOKEN
)

@app.on_message(filters.command("start"))
async def start_command(client, message):
    await message.reply_text(
        "👋 မင်္ဂလာပါ! ကျုပ်က **SONIQ Music Bot** ပါ 🎶\n\n"
        "သီချင်းများ ရှာဖွေနားဆင်နိုင်ရန် အဆင်သင့် ဖြစ်နေပါပြီ ခင်ဗျ။"
    )

if __name__ == "__main__":
    print("🤖 SONIQ Music Bot စတင်အလုပ်လုပ်နေပါပြီ...")
    app.run()
