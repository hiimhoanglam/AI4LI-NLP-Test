# Summary – NLP Pipeline for Vietnamese Text Processing (Assistive Context)

## Author Info
- **Name**: Hoàng Thiết Lâm  
- **University**: University of Science, Vietnam National University, Hanoi  
- **Email**: thietlam04@gmail.com  

---

## Part 1: Vietnamese Text Processing Pipeline

### 🔹 Goal:
Develop a Vietnamese NLP pipeline including:
- Preprocessing  
- Tokenization  
- POS tagging  
- Diacritic restoration  

### Focus:
Tailored for assistive applications (e.g., for people with disabilities), emphasizing:
- Robustness to noisy inputs (ASR/OCR)
- Fast inference
- Simplified output structure

### Preprocessing Steps:
1. **Unicode normalization** (e.g., normalize diacritics using `ftfy`)
2. **Lowercasing** (optional, reduces vocabulary but loses named entity info)
3. **Remove non-word characters** (via regex; preserve punctuation if needed)
4. **Sentence segmentation** (using tools like `underthesea`)
5. **Spell correction** (optional; e.g., VnSpell)
6. **Number normalization** (optional)

### Diacritic Restoration:
- Address ambiguity and noise from ASR/OCR
- Techniques: rule-based, ML (e.g., SVM), DL (e.g., Transformer, BiLSTM)
- Emphasis on lightweight models for real-time needs

### Tokenization:
- Vietnamese-specific challenges (compound nouns, spacing)
- Tools: `underthesea`, `VnCoreNLP`, BPE (for DL models)

### POS Tagging:
- Challenges: context ambiguity, domain variation
- Tools:
  - Fast: `underthesea`, `VnCoreNLP`
  - Accurate: `PhoBERT`, CRF, RoBERTa (slower, GPU-based)
- Recommended: use CPU-friendly models for assistive deployment

---

## Part 2: Vietnamese to Sign Language Structure Conversion

### Structural Differences:
- Vietnamese: SVO, functional words, punctuation
- Sign language: topic-comment or OSV, fewer function words, uses facial expressions instead of punctuation

### Conversion Pipeline:
1. **Preprocessing** (clean text, segment sentences)
2. **Stopword removal** (retain content words, detect expressive markers)
3. **Word reordering** (based on dependency parsing, topic-first ordering)
4. **Tokenization & POS tagging** (for accurate parsing)
5. **Gloss conversion** (uppercase lemmas for signs; use gloss dictionary)
6. **Facial expression annotation** (based on POS, emotion cues)
7. **Output generation** (text format, animation, or avatar-friendly)

---

### Key Focus:
- Real-time processing  
- Lightweight, accurate models  
- Emphasis on accessibility and sign language clarity  
