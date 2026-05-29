part2POE


Project Overview
A WPF desktop chatbot application designed to educate users on cybersecurity topics, detect sentiment, and remember user preferences. Built in C# with .NET Framework.

Features

**1. Multi-Stage UI Flow**
- **Home Grid**: Welcome screen with logo and “Proceed” button
- **Username Grid**: Captures and remembers returning users via `user_names.txt`
- **Chat Grid**: Main conversational interface with styled message bubbles


 2. how it works
1. **Launch**: App plays `greeting.wav` and shows `home_grid`
2. **Onboarding**: User clicks "Proceed" → enters username → app checks `user_names.txt`
3. **Chat**: User types question → app sanitizes input → splits into words → matches against `reply` ArrayList
4. **Interest Capture**: If user says "interested in X", X is saved to `interested_topic.txt`
5. **Sentiment**: Keywords like "frustrated" or "worried" trigger empathetic responses
6. **Response**: Bot picks random matching answer to avoid repetition + scrolls to latest message




3. Key Classes Explained

| Class | Purpose |
| --- | --- |
| `MainWindow` | Handles UI navigation, chat logic, AI matching, interest tracking |
| `respond` | Populates `reply` and `ignore` ArrayLists with chatbot knowledge |
| `user_name` | Manages username persistence and welcome messages |
| `voice_greeting` | Plays `greeting.wav` from `/bin/Debug/` on startup |

4. Example Interactions

**User**: `I am interested in phishing and firewalls`  
**ChatBot**: `great, i added phishing, firewalls to your interests and phishing is a scam where attackers pretend to be trusted sources to steal information.`

**User**: `I'm worried my account was hacked`  
**ChatBot**: `it's okay to feel worried. i'm here to help you stay safe online. hacked account immediately secure your account and log out of all devices.`

**User**: `what is a vpn`  
**ChatBot**: `vpn a vpn helps protect your privacy on public wi-fi.`



5. References

1. Microsoft. (2026). *Windows Presentation Foundation (WPF) Documentation*. Retrieved from https://learn.microsoft.com/en-us/dotnet/desktop/wpf/
2. Microsoft. (2026). *C# Programming Guide*. Retrieved from https://learn.microsoft.com/en-us/dotnet/csharp/
3. National Institute of Standards and Technology. (2018). *NIST Cybersecurity Framework v1.1*. NIST. https://www.nist.gov/cyberframework
4. Hadnagy, C. (2018). *Social Engineering: The Science of Human Hacking*. Wiley.
5. OWASP Foundation. (2023). *OWASP Top Ten Web Application Security Risks*. https://owasp.org/www-project-top-ten/
6. Microsoft. (2026). *SoundPlayer Class (System.Media)*. Retrieved from https://learn.microsoft.com/en-us/dotnet/api/system.media.soundplayer

6. Author
Part 2 AI Chatbot Project  
student name: Conny Dliwayo
Course: Software Development
RoseBank internation 
C
Year: 2026

7. License
This project is for educational purposes. All cybersecurity advice follows standard best practices from NIST and OWASP.
