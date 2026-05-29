# part2POE


Project Overview
A WPF desktop chatbot application designed to educate users on cybersecurity topics, detect sentiment, and remember user preferences. Built in C# with .NET Framework.

## **Features**

### **1. Multi-Stage UI Flow**
- **Home Grid**: Welcome screen with logo and “Proceed” button
- **Username Grid**: Captures and remembers returning users via `user_names.txt`
- **Chat Grid**: Main conversational interface with styled message bubbles

### **2. Cybersecurity Knowledge Base**
Pre-loaded answers for key topics. Each topic has multiple responses for variety:
- **Purpose** - What the chatbot does
- **Cybersecurity** - Core definitions and principles  
- **Phishing** - How to identify and avoid phishing attacks
- **Firewall** - Network traffic control and protection
- **Password** - Best practices for strong credentials
- **Hacked Account** - Immediate steps after compromise
- **Fraud** - Financial security and reporting
- **Malicious Chatbot** - Recognizing fake bots
- **VPN** - Privacy on public networks
- **Ransomware** - Prevention and backup strategies
- **Social Engineering** - Human-based attack tactics
- **Data Breach** - Response and notification steps

### **3. Sentiment Detection**
Detects user emotions and responds empathetically:
- **Positive**: happy, good news
- **Negative**: frustrated, worried, sad, angry, confused
- **Neutral**: factual responses

### **4. Memory & Personalization**
- **User Recall**: Remembers usernames in `user_names.txt` and welcomes returning users
- **Interest Tracking**: Users can say "I am interested in phishing" and the bot saves it to `interested_topic.txt`
- **Auto Reminders**: Every 3 messages, the bot reminds users of their saved interests

### **5. Voice Greeting**
Plays `greeting.wav` on startup using `SoundPlayer` for an audio welcome.

### **6. Input Sanitization**
`RemoveSpecialCharacters()` method strips malicious input and normalizes questions before processing.

## **Project Structure**
## **How It Works**

1. **Launch**: App plays `greeting.wav` and shows `home_grid`
2. **Onboarding**: User clicks "Proceed" → enters username → app checks `user_names.txt`
3. **Chat**: User types question → app sanitizes input → splits into words → matches against `reply` ArrayList
4. **Interest Capture**: If user says "interested in X", X is saved to `interested_topic.txt`
5. **Sentiment**: Keywords like "frustrated" or "worried" trigger empathetic responses
6. **Response**: Bot picks random matching answer to avoid repetition + scrolls to latest message



#
## **Key Classes Explained**

| Class | Purpose |
| --- | --- |
| `MainWindow` | Handles UI navigation, chat logic, AI matching, interest tracking |
| `respond` | Populates `reply` and `ignore` ArrayLists with chatbot knowledge |
| `user_name` | Manages username persistence and welcome messages |
| `voice_greeting` | Plays `greeting.wav` from `/bin/Debug/` on startup |

## **Example Interactions**

**User**: `I am interested in phishing and firewalls`  
**ChatBot**: `great, i added phishing, firewalls to your interests and phishing is a scam where attackers pretend to be trusted sources to steal information.`

**User**: `I'm worried my account was hacked`  
**ChatBot**: `it's okay to feel worried. i'm here to help you stay safe online. hacked account immediately secure your account and log out of all devices.`

**User**: `what is a vpn`  
**ChatBot**: `vpn a vpn helps protect your privacy on public wi-fi.`

## **Limitations & Future Improvements**

1. **Keyword-based**: Current AI uses simple word matching, not NLP. Upgrade to ML.NET or Azure Cognitive Services for better intent detection.
2. **Text file storage**: Replace `user_names.txt` with SQLite or JSON for scalability.
3. **No encryption**: User data is plaintext. Add encryption for `interested_topic.txt` in production.
4. **UI**: ListView could be upgraded to a proper chat bubble control for better UX.

## **References**

1. Microsoft. (2026). *Windows Presentation Foundation (WPF) Documentation*. Retrieved from https://learn.microsoft.com/en-us/dotnet/desktop/wpf/
2. Microsoft. (2026). *C# Programming Guide*. Retrieved from https://learn.microsoft.com/en-us/dotnet/csharp/
3. National Institute of Standards and Technology. (2018). *NIST Cybersecurity Framework v1.1*. NIST. https://www.nist.gov/cyberframework
4. Hadnagy, C. (2018). *Social Engineering: The Science of Human Hacking*. Wiley.
5. OWASP Foundation. (2023). *OWASP Top Ten Web Application Security Risks*. https://owasp.org/www-project-top-ten/
6. Microsoft. (2026). *SoundPlayer Class (System.Media)*. Retrieved from https://learn.microsoft.com/en-us/dotnet/api/system.media.soundplayer

## **Author**
Part 2 AI Chatbot Project  
student name: Conny Dliwayo
Course: Software Development
RoseBank internation 
C
Year: 2026

## **License**
This project is for educational purposes. All cybersecurity advice follows standard best practices from NIST and OWASP.
