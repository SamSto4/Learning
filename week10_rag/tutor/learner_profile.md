# Learner profile: Sam

## Preferences
- Python comfort: 1 out of 5 (has never learned Python). Explain every line and every bit of syntax; go slowly.
- Learning style: try first, then see an example.
- Language: English.
- Interests (for examples): rock and metal music, Red Hot Chili Peppers (favourite band), plays guitar, Attack on Titan, Fight Club, chess sometimes.

## Working setup
- Cloud chat with no editor: Sam types code lines in the chat, and Claude puts them into the lab file exactly as written.
- Run with `.venv/bin/python` from inside `week10_rag`.
- Commit and push lab progress to `main` at the end of each part.

## Progress (Lab 1)
- Checkpoint 0 (setup): done.
- Concept 1 (Why RAG): done. Answered correctly that Claude can't answer about Nimbus Robotics because it was never in its training data.
- Concept 2 (Embeddings): done. Correctly said "Unable to sign in" and "I forgot my login credentials" score close together.
- Concepts 3-5 (chunking, vector DBs, pipeline): done. Needed a nudge that the model ignores text past ~1,100 chars, and that only the new file needs indexing.
- Part 1 (TODO 1, similarity): done. First wrote return np.dot(a,b), then added float(...) after one hint. Predicted pair 4 lowest (correct), pair 2 highest (actual: pair 3).
- Part 2 (TODO 2, chunk_text): done (also tidied: removed hard-coded size/overlap). Wrote a JavaScript-style draft (set keyword, curly braces); fixed each error on their own by reading the clue. Traced the end bug by hand (end = start + size). Errors-as-clues approach works well for Sam.
- Part 3a (build_index col.add): done. Struggled with f-strings (forgot { } around doc['source']) and list comprehensions; got there with tiny steps and demo outputs. Asked good "what do I have access to?" questions.
