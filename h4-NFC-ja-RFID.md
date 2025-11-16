# a) Tarkastele käytössäsi olevia RFID tuotteita, mieti miten hyvin olet suojautunut RFID urkinnalta?
All my RFID products are just things like banking credit and debit cards and i have owned an RFID blocking wallet for a long time and as far as i know those work just great so i would say i'm pretty well protected.
# b) Tutustu APDU komentojen rakenteeseen.
- APDU (or application protocol data unit) is a unit used for communications between a smart card reader and a smart card
- There are two categories: command- and response APDUs
- Command APDUs conatain four mandatory lines CLA, INS, P1 and P2 and they can also have optional lines Lc, Data and Le
- Response APDUs contain three lines Data, two of which are mandatory SW1 and SW2
# c) Tutki ja kerro minkä mielenkiintoisen RFID hakkerointi uutiset löysit.
I found this very old article about "hack-proof" RFID chips writen by Larry Hardesty for the MIT News: https://news.mit.edu/2016/hack-proof-rfid-chips-0203

The article talks about a chip desinged to prevent side-channel attacks that are attacks that analyze patterns of memory access and power usage when performing a cryptographic operation to extract it's cryptographic key.
The article also talks about an exploit that would still be possible for such a chip called "power glitch" attack in which the chip's power is repeatedly cut allowing the attacker to run the side-channel attack thousands of times.

The one thing i tried to research about this article since it is so old is what happened after the chips after this discovery. There were loads of articles writen by other news outlets about the chip but i wasn't able to find
any new developments or follow ups with it.

# sources 
Karvinen T. Verkkoon tunkeutuminen ja tiedustelu: https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/

wikipedia. Smart card application protocol data unit: https://en.wikipedia.org/wiki/Smart_card_application_protocol_data_unit

Hardesty L. 3.02.2016 Toward hack-proof RFID chips. MIT News: https://news.mit.edu/2016/hack-proof-rfid-chips-0203
