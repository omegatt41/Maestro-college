```dataviewjs
// 1. Common English words to exclude
const stopWords = new Set([
    "about", "above", "after", "again", "against", "all", "am", "an", "and", "any", "are", "as", "at", "be", "because", "been", "before", "being", "below", "between", "both", "but", "by", "can", "did", "do", "does", "doing", "down", "during", "each", "few", "for", "from", "further", "had", "has", "have", "having", "he", "her", "here", "hers", "him", "his", "how", "if", "in", "into", "is", "it", "its", "more", "most", "my", "no", "nor", "not", "of", "off", "on", "once", "only", "or", "other", "ought", "our", "ours", "out", "over", "own", "same", "she", "should", "so", "some", "such", "than", "that", "the", "their", "theirs", "them", "then", "there", "these", "they", "this", "those", "through", "too", "under", "until", "very", "was", "we", "were", "what", "when", "where", "which", "while", "who", "whom", "why", "with", "would", "you", "your", "yours"
]);

// 2. Get all markdown files
const files = app.vault.getMarkdownFiles();
const vocabulary = new Set();

for (const file of files) {
    const content = await app.vault.cachedRead(file);
    
    // Regex: Matches everything inside **bold** markers
    const boldRegex = /\*\*([\w\s-]+)\*\*/g;
    let match;

    while ((match = boldRegex.exec(content)) !== null) {
        const fullPhrase = match[1].trim();
        
        // Only include if the entire bolded phrase is > 5 letters
        // and is not in our common stopWords list
        if (fullPhrase.length > 5 && !stopWords.has(fullPhrase.toLowerCase())) {
            vocabulary.add(fullPhrase);
        }
    }
}

// 3. Sort alphabetically and display as a simple list
const sortedVocab = Array.from(vocabulary).sort((a, b) => 
    a.toLowerCase().localeCompare(b.toLowerCase())
);

dv.header(2, "Exam Vocabulary List (" + sortedVocab.length + " terms)");
dv.list(sortedVocab);
