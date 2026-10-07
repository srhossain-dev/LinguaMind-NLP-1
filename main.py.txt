def analyze_sentiment(text):
    """Analyzes text sentiment using a basic bilingual lexical dataset."""
    
    positive_lexicon = ["good", "great", "happy", "love", 
                       "gut", "perfekt", "glÃ¼cklich", "liebe"]
    negative_lexicon = ["bad", "sad", "terrible", "hate", 
                       "schlecht", "traurig", "schrecklich", "hasse"]

    text_lower = text.lower()
    words = text_lower.split()
    
    score = 0
    
    for word in words:
        if word in positive_lexicon:
            score += 1
        elif word in negative_lexicon:
            score -= 1
            
    if score > 0:
        return "Positive ðŸ¢""
    elif score < 0:
        return "Negative ðŸ¢""
    else:
        return "Neutral âš¾è¸ "

# Output Display
print("""t----------------------------------------------------------------------------------
ðŸ§´ LINGUAMIND: BILINGUAL NLP SENTIMENT ANALYZER ðŸ§´
----------------------------------------------------------------------------------
Lexical Database Loaded: English (EN) & German (DE)

Input Text Data (EN/DE)                          | Sentiment
Analysis\n""")

test_sentences = [
    "[EN] I love the new software curriculum.",
    "[DE] Das wetter heute ist sehr schlecht und traurig.",
    "[EN] Today is a very normal day for me.",
    "[DE] Ich liebe Programmierung, es ist perfekt."
]

for sentence in test_sentences:
    sentiment = analyze_sentiment(sentence)
    print(f"{sentence:<60} | {sentiment}")

print("\nSystem executed successfully. NLP Engine developed by Shahriar")
