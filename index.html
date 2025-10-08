import React, { useState, useEffect, useMemo } from "react";

/*
  Devalicath - Chapter scaffold (single-file React)
  - A single-page scaffold for one Chapter containing 5 sections:
    1. Vocab, 2. Lesson, 3. Example, 4. Application, 5. Exercise
  - Tailwind CSS classes assumed available.
  - Replace sample placeholders with your real content.
  - Audio: UI supports uploading audio per vocab item (you will record & upload later).
  - Chatbot: lightweight local mock chatbot widget (replace with real chatbot integration as needed).
*/

export default function DevalicathChapter() {
  // --- Data scaffold (you will paste your real content here) ---
  const emptyVocab = Array.from({ length: 8 }).map((_, i) => ({
    id: `w${i + 1}`,
    word: `word_${i + 1}`,
    meaning: `Nghía tiếng Việt ${i + 1}`,
    audioUrl: "", // upload later
  }));

  // local state
  const [vocab, setVocab] = useState(emptyVocab);
  const [mode, setMode] = useState("match"); // match | flashcard | practice
  const [search, setSearch] = useState("");

  const [videoUrl, setVideoUrl] = useState(""); // paste your teaching video embed url

  // Example activity state
  const [selectedExampleType, setSelectedExampleType] = useState("scramble");
  const [scrambleInput, setScrambleInput] = useState("");
  const [fillBlank, setFillBlank] = useState("");
  const [mcqAnswer, setMcqAnswer] = useState("");

  // Exercise / Quiz scaffold
  const sampleQuestions = [
    {
      id: 1,
      type: "mcq",
      q: "Which is the correct value?",
      options: ["A", "B", "C", "D"],
      answer: "A",
    },
    { id: 2, type: "tf", q: "True or False sample.", answer: "True" },
    { id: 3, type: "short", q: "Explain briefly...", answer: "" },
  ];
  const [questions] = useState(sampleQuestions);
  const [responses, setResponses] = useState({});

  // Chatbot (simple local mock) --- replace with real chatbot widget / API
  const [chatOpen, setChatOpen] = useState(false);
  const [chatMessages, setChatMessages] = useState([
    { from: "bot", text: "Hi! Ask me about the lesson or exercises." },
  ]);
  const [chatInput, setChatInput] = useState("");

  // Persist vocab to localStorage so your uploads survive refresh while editing
  useEffect(() => {
    const saved = localStorage.getItem("devalicath_vocab");
    if (saved) setVocab(JSON.parse(saved));
  }, []);
  useEffect(() => {
    localStorage.setItem("devalicath_vocab", JSON.stringify(vocab));
  }, [vocab]);

  // helpers
  function handleAudioUpload(file, id) {
    // store as local blob URL for demo; in production upload to your server or S3.
    const url = URL.createObjectURL(file);
    setVocab((v) => v.map((w) => (w.id === id ? { ...w, audioUrl: url } : w)));
  }

  function playAudio(url) {
    if (!url) return alert("No audio uploaded yet. Upload an MP3 or record and add it.");
    new Audio(url).play();
  }

  function addVocabRow() {
    setVocab((v) => [...v, { id: `w${v.length + 1}`, word: "new_word", meaning: "nghĩa", audioUrl: "" }]);
  }

  function removeVocab(id) {
    setVocab((v) => v.filter((x) => x.id !== id));
  }

  // Chatbot mock response
  function sendChat() {
    if (!chatInput.trim()) return;
    const userMsg = { from: "user", text: chatInput };
    setChatMessages((m) => [...m, userMsg]);
    setChatInput("");
    // simple canned reply logic for demo purposes
    setTimeout(() => {
      const reply = { from: "bot", text: `Bot: I heard '${userMsg.text}'. I can help with vocab, examples, or exercises. Try asking 'explain word_X' or 'give hint for Q1'.` };
      setChatMessages((m) => [...m, reply]);
    }, 600);
  }

  // Filtering
  const filteredVocab = useMemo(() => vocab.filter((w) => w.word.toLowerCase().includes(search.toLowerCase()) || w.meaning.toLowerCase().includes(search.toLowerCase())), [vocab, search]);

  // Flashcard helper
  const [flashIndex, setFlashIndex] = useState(0);
  const nextFlash = () => setFlashIndex((i) => (i + 1) % vocab.length);
  const prevFlash = () => setFlashIndex((i) => (i - 1 + vocab.length) % vocab.length);

  // Simple shuffle for match game
  const shuffle = (arr) => [...arr].sort(() => Math.random() - 0.5);
  const [matchPairs, setMatchPairs] = useState(() => ({ left: [], right: [], mapping: {} }));
  useEffect(() => {
    const left = vocab.map((v) => ({ id: v.id, text: v.word }));
    const right = vocab.map((v) => ({ id: v.id, text: v.meaning }));
    setMatchPairs({ left: shuffle(left), right: shuffle(right), mapping: {} });
  }, [vocab]);

  // --- UI ---
  return (
    <div className="min-h-screen bg-gradient-to-b from-white to-slate-50 text-slate-900">
      <header className="bg-indigo-600 text-white p-6">
        <div className="max-w-6xl mx-auto flex items-center justify-between">
          <h1 className="text-2xl font-extrabold">Devalicath — Chapter Editor</h1>
          <div className="text-sm opacity-90">Chapter scaffold (Vocab / Lesson / Example / Application / Exercise)</div>
        </div>
      </header>

      <main className="max-w-6xl mx-auto p-6 grid grid-cols-1 lg:grid-cols-3 gap-6">
        {/* Left: Main content (two columns merged on large screens) */}
        <section className="lg:col-span-2 space-y-6">
          {/* Vocab Section */}
          <article className="bg-white rounded-2xl p-6 shadow">
            <div className="flex items-center justify-between">
              <h2 className="text-lg font-semibold">1. Vocab</h2>
              <div className="text-sm text-slate-500">Mode:</div>
            </div>

            <div className="mt-4 flex gap-2 items-center">
              <input value={search} onChange={(e) => setSearch(e.target.value)} placeholder="Search vocab or meaning" className="flex-1 rounded-md border p-2" />
              <button onClick={addVocabRow} className="px-3 py-1 rounded-md bg-indigo-600 text-white">Add word</button>
            </div>

            <div className="mt-4 flex gap-2">
              <button onClick={() => setMode("match")} className={`px-3 py-1 rounded-md ${mode === "match" ? "bg-indigo-600 text-white" : "bg-slate-100"}`}>Match</button>
              <button onClick={() => setMode("flashcard")} className={`px-3 py-1 rounded-md ${mode === "flashcard" ? "bg-indigo-600 text-white" : "bg-slate-100"}`}>Flashcard</button>
              <button onClick={() => setMode("practice")} className={`px-3 py-1 rounded-md ${mode === "practice" ? "bg-indigo-600 text-white" : "bg-slate-100"}`}>Practice</button>
            </div>

            {/* Data table for vocab (editable) */}
            <div className="mt-4 overflow-x-auto">
              <table className="w-full table-auto">
                <thead className="text-left text-sm text-slate-500">
                  <tr>
                    <th className="p-2">Word</th>
                    <th className="p-2">Meaning (VI)</th>
                    <th className="p-2">Audio</th>
                    <th className="p-2">Actions</th>
                  </tr>
                </thead>
                <tbody>
                  {filteredVocab.map((w) => (
                    <tr key={w.id} className="border-t">
                      <td className="p-2">
                        <input value={w.word} onChange={(e) => setVocab((vs) => vs.map((x) => (x.id === w.id ? { ...x, word: e.target.value } : x)))} className="w-full p-2 rounded-md border" />
                      </td>
                      <td className="p-2">
                        <input value={w.meaning} onChange={(e) => setVocab((vs) => vs.map((x) => (x.id === w.id ? { ...x, meaning: e.target.value } : x)))} className="w-full p-2 rounded-md border" />
                      </td>
                      <td className="p-2 flex items-center gap-2">
                        <input type="file" accept="audio/*" onChange={(e) => handleAudioUpload(e.target.files[0], w.id)} />
                        <button onClick={() => playAudio(w.audioUrl)} className="px-3 py-1 rounded-md border">🔊 Play</button>
                      </td>
                      <td className="p-2">
                        <button onClick={() => removeVocab(w.id)} className="px-3 py-1 rounded-md bg-red-50 text-red-600">Remove</button>
                      </td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>

            {/* Mode UIs */}
            <div className="mt-6">
              {mode === "match" && (
                <div>
                  <h4 className="font-medium">Match — drag & drop style (click to mark pairs)</h4>
                  <div className="grid grid-cols-2 gap-4 mt-4">
                    <div className="bg-slate-50 p-4 rounded-lg">
                      <h5 className="text-sm font-semibold">Words</h5>
                      <ul className="mt-2 space-y-2">
                        {matchPairs.left.map((l) => (
                          <li key={l.id} className="p-2 bg-white rounded-md shadow-sm">{l.text}</li>
                        ))}
                      </ul>
                    </div>
                    <div className="bg-slate-50 p-4 rounded-lg">
                      <h5 className="text-sm font-semibold">Meanings</h5>
                      <ul className="mt-2 space-y-2">
                        {matchPairs.right.map((r) => (
                          <li key={r.id} className="p-2 bg-white rounded-md shadow-sm">{r.text}</li>
                        ))}
                      </ul>
                    </div>
                  </div>
                  <p className="mt-3 text-sm text-slate-500">(This is a static scaffold. You can later hook a drag&drop or click-to-match library to this list.)</p>
                </div>
              )}

              {mode === "flashcard" && (
                <div className="flex flex-col items-center gap-4">
                  <div className="w-full bg-white p-6 rounded-2xl shadow text-center">
                    <div className="text-sm text-slate-400">Flashcard — meaning shown first</div>
                    {vocab.length > 0 ? (
                      <div className="mt-3">
                        <div className="text-2xl font-bold">{vocab[flashIndex].meaning}</div>
                        <div className="mt-2 text-sm text-slate-500">(Flip to reveal word)</div>
                        <div className="mt-4 flex gap-2 justify-center">
                          <button onClick={prevFlash} className="px-4 py-2 rounded-md border">Prev</button>
                          <button onClick={() => alert(`Reveal: ${vocab[flashIndex].word}`)} className="px-4 py-2 rounded-md bg-indigo-600 text-white">Flip</button>
                          <button onClick={nextFlash} className="px-4 py-2 rounded-md border">Next</button>
                          <button onClick={() => playAudio(vocab[flashIndex].audioUrl)} className="px-4 py-2 rounded-md border">🔊</button>
                        </div>
                      </div>
                    ) : (
                      <div className="text-slate-500">No vocab yet — add words above.</div>
                    )}
                  </div>
                </div>
              )}

              {mode === "practice" && (
                <div>
                  <h4 className="font-medium">Practice — quick review</h4>
                  <div className="mt-3 grid grid-cols-1 sm:grid-cols-2 gap-4">
                    {vocab.slice(0, 8).map((w) => (
                      <div key={w.id} className="p-3 bg-white rounded-md shadow-sm flex items-center justify-between">
                        <div>
                          <div className="font-semibold">{w.word}</div>
                          <div className="text-sm text-slate-500">{w.meaning}</div>
                        </div>
                        <div className="flex gap-2">
                          <button onClick={() => playAudio(w.audioUrl)} className="px-3 py-1 rounded-md border">🔊</button>
                        </div>
                      </div>
                    ))}
                  </div>
                </div>
              )}
            </div>
          </article>

          {/* Lesson Section */}
          <article className="bg-white rounded-2xl p-6 shadow">
            <h2 className="text-lg font-semibold">2. Lesson</h2>
            <p className="text-sm text-slate-500 mt-2">Paste your teaching video link (YouTube/Vimeo) or upload a video file. You can add multiple resources below.</p>

            <div className="mt-4">
              <input value={videoUrl} onChange={(e) => setVideoUrl(e.target.value)} placeholder="YouTube embed url (https://www.youtube.com/watch?v=...)" className="w-full rounded-md border p-2" />
            </div>

            {videoUrl && (
              <div className="mt-4">
                <div className="aspect-video w-full rounded-lg overflow-hidden">
                  <iframe title="lesson-video" src={convertYouTubeEmbed(videoUrl)} className="w-full h-full" frameBorder="0" allowFullScreen />
                </div>
              </div>
            )}

            <div className="mt-4">
              <label className="block text-sm font-medium">Teacher notes / lesson chapters (paste HTML or plain text)</label>
              <textarea placeholder="Your lesson outline or notes..." className="mt-2 w-full rounded-md border p-3 h-28"></textarea>
            </div>
          </article>

          {/* Example Section */}
          <article className="bg-white rounded-2xl p-6 shadow">
            <h2 className="text-lg font-semibold">3. Example</h2>
            <p className="text-sm text-slate-500 mt-2">Interactive example templates you can fill: scramble sentence, fill-in-the-blank, choose missing word, short answer, vocab-match.</p>

            <div className="mt-4 flex gap-2">
              <button onClick={() => setSelectedExampleType("scramble")} className={`px-3 py-1 rounded-md ${selectedExampleType === "scramble" ? "bg-indigo-600 text-white" : "bg-slate-100"}`}>Scramble</button>
              <button onClick={() => setSelectedExampleType("fill") } className={`px-3 py-1 rounded-md ${selectedExampleType === "fill" ? "bg-indigo-600 text-white" : "bg-slate-100"}`}>Fill blank</button>
              <button onClick={() => setSelectedExampleType("mcq")} className={`px-3 py-1 rounded-md ${selectedExampleType === "mcq" ? "bg-indigo-600 text-white" : "bg-slate-100"}`}>Choose</button>
              <button onClick={() => setSelectedExampleType("short")} className={`px-3 py-1 rounded-md ${selectedExampleType === "short" ? "bg-indigo-600 text-white" : "bg-slate-100"}`}>Short answer</button>
            </div>

            <div className="mt-4">
              {selectedExampleType === "scramble" && (
                <div>
                  <label className="text-sm">Enter the correct sentence (will be scrambled for the learner)</label>
                  <input value={scrambleInput} onChange={(e) => setScrambleInput(e.target.value)} className="w-full rounded-md border p-2 mt-2" placeholder="E.g. The quick brown fox jumps over the lazy dog." />
                  <div className="mt-3">
                    <button onClick={() => alert(scrambleForLearner(scrambleInput))} className="px-4 py-2 rounded-md bg-indigo-600 text-white">Preview scrambled</button>
                  </div>
                </div>
              )}

              {selectedExampleType === "fill" && (
                <div>
                  <label className="text-sm">Fill-in-the-blank template (use __ for blanks)</label>
                  <input value={fillBlank} onChange={(e) => setFillBlank(e.target.value)} className="w-full rounded-md border p-2 mt-2" placeholder="E.g. The area of a circle is __ * r^2." />
                  <div className="mt-3"><button onClick={() => alert(`Preview: ${fillBlank}`)} className="px-4 py-2 rounded-md bg-indigo-600 text-white">Preview</button></div>
                </div>
              )}

              {selectedExampleType === "mcq" && (
                <div>
                  <div className="text-sm text-slate-500">Sample MCQ preview (edit in code to add real MCQs)</div>
                  <div className="mt-3 bg-slate-50 p-4 rounded-md">
                    <div className="font-medium">Q: What is 2 + 3?</div>
                    <div className="mt-2 grid grid-cols-2 gap-2">
                      <button className="p-2 rounded-md border">A. 4</button>
                      <button className="p-2 rounded-md border">B. 5</button>
                      <button className="p-2 rounded-md border">C. 6</button>
                      <button className="p-2 rounded-md border">D. 7</button>
                    </div>
                  </div>
                </div>
              )}

              {selectedExampleType === "short" && (
                <div>
                  <label className="text-sm">Short-answer prompt</label>
                  <textarea placeholder="E.g. Explain why the derivative of x^2 is 2x..." className="w-full rounded-md border p-2 mt-2 h-28"></textarea>
                </div>
              )}
            </div>
          </article>

          {/* Application Section */}
          <article className="bg-white rounded-2xl p-6 shadow">
            <h2 className="text-lg font-semibold">4. Application</h2>
            <p className="text-sm text-slate-500 mt-2">Real-world tasks — paste two videos and attach applied math problems below.</p>

            <div className="mt-4 grid grid-cols-1 md:grid-cols-2 gap-4">
              <div>
                <label className="text-sm">Video 1 URL</label>
                <input placeholder="Paste YouTube/Vimeo URL" className="w-full rounded-md border p-2 mt-1" />
              </div>
              <div>
                <label className="text-sm">Video 2 URL</label>
                <input placeholder="Paste YouTube/Vimeo URL" className="w-full rounded-md border p-2 mt-1" />
              </div>
            </div>

            <div className="mt-4">
              <label className="text-sm">Applied problem set (editable)</label>
              <textarea placeholder="Write applied tasks here (students will solve after watching videos)" className="w-full rounded-md border p-3 h-36 mt-2"></textarea>
            </div>
          </article>

          {/* Exercise Section */}
          <article className="bg-white rounded-2xl p-6 shadow">
            <h2 className="text-lg font-semibold">5. Exercise</h2>
            <p className="text-sm text-slate-500 mt-2">Practice tests: multiple choice, true/false, short answer. Students can submit answers and get basic feedback (you can extend scoring logic).</p>

            <div className="mt-4 space-y-4">
              {questions.map((q) => (
                <div key={q.id} className="p-4 bg-slate-50 rounded-md">
                  <div className="font-medium">Q{q.id}. {q.q}</div>
                  <div className="mt-2">
                    {q.type === "mcq" && q.options.map((opt) => (
                      <label key={opt} className="flex items-center gap-2">
                        <input type="radio" name={`q${q.id}`} onChange={() => setResponses((r) => ({ ...r, [q.id]: opt }))} />
                        <span>{opt}</span>
                      </label>
                    ))}

                    {q.type === "tf" && (
                      <div className="flex gap-3">
                        <label className="flex items-center gap-2"><input type="radio" name={`q${q.id}`} onChange={() => setResponses((r) => ({ ...r, [q.id]: "True" }))} /> True</label>
                        <label className="flex items-center gap-2"><input type="radio" name={`q${q.id}`} onChange={() => setResponses((r) => ({ ...r, [q.id]: "False" }))} /> False</label>
                      </div>
                    )}

                    {q.type === "short" && (
                      <textarea onChange={(e) => setResponses((r) => ({ ...r, [q.id]: e.target.value }))} className="w-full rounded-md border p-2 mt-2"></textarea>
                    )}
                  </div>
                </div>
              ))}

              <div>
                <button onClick={() => alert(`Student responses: ${JSON.stringify(responses)}`)} className="px-4 py-2 rounded-md bg-indigo-600 text-white">Submit Answers</button>
              </div>
            </div>
          </article>
        </section>

        {/* Right Sidebar: Quick settings + Chat hint */}
        <aside className="space-y-6">
          <div className="bg-white rounded-2xl p-4 shadow">
            <h3 className="font-semibold">Chapter Settings</h3>
            <div className="mt-3 text-sm text-slate-600">
              <label className="block">Chapter title</label>
              <input placeholder="Chapter name..." className="w-full rounded-md border p-2 mt-1" defaultValue="Devalicath Chapter 1" />

              <label className="block mt-3">Tags (comma separated)</label>
              <input placeholder="e.g. algebra, functions" className="w-full rounded-md border p-2 mt-1" />
            </div>
          </div>

          <div className="bg-white rounded-2xl p-4 shadow">
            <h3 className="font-semibold">Quick actions</h3>
            <div className="mt-3 flex flex-col gap-2">
              <button onClick={() => { localStorage.removeItem('devalicath_vocab'); alert('Saved vocab cleared.'); }} className="px-3 py-2 rounded-md border">Clear saved vocab</button>
              <button onClick={() => alert('Export not implemented in demo. You can copy content from inputs.') } className="px-3 py-2 rounded-md bg-indigo-600 text-white">Export chapter</button>
            </div>
          </div>

          <div className="bg-white rounded-2xl p-4 shadow text-sm text-slate-600">
            <div className="font-semibold">Chatbot</div>
            <div className="mt-2">A small help-chat is available bottom-right for students to ask questions while doing exercises. Replace with your chatbot provider for AI-powered help (Dialogflow, Rasa, or OpenAI backend).</div>
          </div>
        </aside>
      </main>

      <footer className="max-w-6xl mx-auto p-6 text-center text-sm text-slate-500">Devalicath — made for teachers. Replace this scaffold with your full content.</footer>

      {/* Chat widget (bottom-right) */}
      <div className={`fixed right-6 bottom-6 w-80 ${chatOpen ? "h-96" : "h-14"} transition-all`}> 
        <div className="bg-white rounded-2xl shadow-lg overflow-hidden flex flex-col h-full">
          <div className="px-4 py-3 bg-indigo-600 text-white flex items-center justify-between">
            <div className="font-semibold">Devalicath Bot</div>
            <div className="flex gap-2 items-center">
              <button onClick={() => { setChatMessages([{ from: 'bot', text: 'Hi! Ask me about the lesson.' }]); }} className="text-sm opacity-80">Reset</button>
              <button onClick={() => setChatOpen((s) => !s)} className="text-white text-xl">{chatOpen ? '—' : '✧'}</button>
            </div>
          </div>

          {chatOpen ? (
            <div className="flex-1 p-3 flex flex-col">
              <div className="flex-1 overflow-y-auto space-y-2">
                {chatMessages.map((m, i) => (
                  <div key={i} className={`p-2 rounded-md ${m.from === 'bot' ? 'bg-slate-100 self-start' : 'bg-indigo-600 text-white self-end'}`}>{m.text}</div>
                ))}
              </div>
              <div className="mt-2 flex gap-2">
                <input value={chatInput} onChange={(e) => setChatInput(e.target.value)} placeholder="Ask a question..." className="flex-1 rounded-md border p-2" />
                <button onClick={sendChat} className="px-3 py-2 rounded-md bg-indigo-600 text-white">Send</button>
              </div>
            </div>
          ) : (
            <div className="p-3 text-sm">Need help? Click to open chat.</div>
          )}
        </div>
      </div>
    </div>
  );
}

// --- Utility functions below ---
function convertYouTubeEmbed(url) {
  try {
    if (!url) return "";
    // If it's a full URL like https://www.youtube.com/watch?v=VIDEOID
    const u = new URL(url);
    if (u.hostname.includes('youtube.com')) {
      const v = u.searchParams.get('v');
      if (v) return `https://www.youtube.com/embed/${v}`;
    }
    if (u.hostname.includes('youtu.be')) {
      const id = u.pathname.slice(1);
      if (id) return `https://www.youtube.com/embed/${id}`;
    }
    // otherwise return the original (may already be an embed URL)
    return url;
  } catch (e) {
    return url;
  }
}

function scrambleForLearner(sentence) {
  if (!sentence) return "(no sentence)";
  const words = sentence.split(/\s+/).filter(Boolean);
  const scrambled = words.sort(() => Math.random() - 0.5).join('  ');
  return scrambled;
}
