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
- Part 3b (search): done. First draft mixed f-strings with list indexing; switched to a fill-in-the-blanks template, then fixed text, source and score one at a time. All 3 parts work.
- Wrap-up: teach-back gave the core idea (vectors compare meaning, new data can be added); filled in the full pipeline. Mini-quiz 5/5.

## Lab 1 summary for next time
- Clicked: embeddings and similarity, overlap, why store the source, reading error messages as clues.
- Revisit in Lab 2: f-strings (only the parts inside { } get filled in), list comprehensions, and indexing nested lists (res["documents"][0][i]).
- Pace: steady; works best with tiny steps, demo outputs and fill-in-the-blank templates for multi-line code.
- Next: Day 2, Lab 2 (answer with sources). Bring 5-20 English documents in my_docs/ for the final project.

## Progress (Lab 2)
- Concepts 1-5: done. Needed clarification that "I don't know" beats a wrong confident answer, and that the lab makes 4 calls to one separate Claude (no API).
- Part 1 (TODO 1, build_prompt): done. Asked for a skeleton, then filled the blanks; fixed slot order, quotes around "</document>", and a missing \n.
- Part 2 (TODO 2, answer): done. Wrote all 3 lines correctly, one at a time. Predicted the weak prompt would cite sources (it did not) and that the CEO answer would be long (correct).
- Part 3 (TODO 3, SYSTEM_PROMPT): done. Wrote the 5 rules plus 2 of their own (helpful, friendly tone). Answers now cite [file] sources and the CEO question gets exactly "I don't know based on the documents."
- Wrap-up: teach-back named retrieve (search), augment (build_prompt) and generate (Claude) correctly. Mini-quiz 4/4.

## Lab 2 summary for next time
- Clicked: the RAG pipeline end to end, grounding rules, why "I don't know" and citations matter, prompt injection.
- Revisit: one statement per line, quotes around text, building strings with += and "\n".
- Pace: faster than Lab 1; skeletons with blanks still help for multi-line code.
- Next: final project "Ask My Docs" (tutor/project_ask_my_docs.md). Bring 5-20 English documents in my_docs/.

## Progress (Final project: Ask My Docs)
- Documents: 5 notes typed by Sam in my_docs/ (rhcp, guitar_techniques, attack_on_titan, fight_club, chess), 58 chunks.
- qa_bot.py TODO 1 and TODO 2: done. Tripped on f-string quotes and indentation; Claude fixed the loop spacing at Sam's request. Bot answers with citations and says "I don't know".
- Testing: my_questions.json hit@3 = 5/5 (questions reused exact words). Hard-mode hard_questions.json also 3/3 at file level, but the answer chunk was missing from the top 3 for 2 of 3 questions.
- Failure found: the Titans "13 more years" question got "I don't know" (retrieval failure; the curse sentence sits in a chunk dominated by the Nine Titans table). Fix tried: rephrased with "inherit" and "curse", and the answer chunk moved to #1 (0.39); the bot answered "13 more years [attack_on_titan.md]".
- Also noticed: rules 6-7 (helpful, friendly) make the "I don't know" reply add extra sentences instead of the exact fixed line.

## Progress (Week 11 Lab 1: memory)
- Setup: Claude copied the week11_memory kit into the repo, made .venv (Python 3.13), setup_check all OK. Profile copied from week10_rag.
- Concepts 1-4 (stateless, in-context memory, external memory types, schemas): all check questions right on the first try.
- Part 1 (TODO 1, build_prompt): asked for the blanks after the hints, then typed the lines. A stray "goes last" (lost #) gave a SyntaxError; fixed it by reading the ^^^^ arrows. Predictions 2/2.
- Part 2 (TODO 2a, 2b): load_memory first used encoding="string["; fixed to "utf-8" after reading the LookupError. save_memory right the first time. Saw run #1 -> run #2.
- Part 3 (TODO 3, extract_facts): right the first time. Privacy check passed (kept chess, dropped the password).
- Wrap-up: teach-back gave the core idea (save facts to a file); needed the reminder that facts must be loaded back into the prompt. Mini-quiz 5/5.

## Week 11 Lab 1 summary for next time
- Clicked: stateless model, sliding window, semantic vs episodic memory, JSON schema, load/save as opposites.
- Revisit: comments need a # (copied lines lost it), encoding names ("utf-8"), getting values out of a dict (m["content"]).
- Pace: faster than Week 10; one-line skeletons with blanks work well. Skipped the boss challenge (compaction).
- Next: Week 11 Lab 2, "Plan my evening" (tutor/lab2_planner.md), episodic memory.
