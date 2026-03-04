import { useState, useEffect, useCallback, useRef } from "react";

// ═══════════════════════════════════════════════════════════════
// ESCAPE FLAB — French -ER Verbs au Présent (A1.1.1)
// For English speakers learning French
// ═══════════════════════════════════════════════════════════════

// ── DATA ──────────────────────────────────────────────────────

const ER_VERB_ENDINGS = [
  { subject: "Je", ending: "-e", example: "Je parle", exampleEn: "I speak" },
  { subject: "Tu", ending: "-es", example: "Tu parles", exampleEn: "You speak" },
  { subject: "Il / Elle / On", ending: "-e", example: "Il parle", exampleEn: "He speaks" },
  { subject: "Nous", ending: "-ons", example: "Nous parlons", exampleEn: "We speak" },
  { subject: "Vous", ending: "-ez", example: "Vous parlez", exampleEn: "You speak (formal)" },
  { subject: "Ils / Elles", ending: "-ent", example: "Ils parlent", exampleEn: "They speak" },
];

const VISUAL_VOCAB = [
  { verb: "Cuisiner", translation: "To cook", icon: "🍳", pronunciation: "kwee-zee-nay" },
  { verb: "Étudier", translation: "To study", icon: "📖", pronunciation: "ay-tew-dee-ay" },
  { verb: "Voyager", translation: "To travel", icon: "✈️", pronunciation: "voy-ah-jay" },
  { verb: "Écouter", translation: "To listen", icon: "🎧", pronunciation: "ay-koo-tay" },
  { verb: "Regarder", translation: "To watch", icon: "📺", pronunciation: "ruh-gar-day" },
  { verb: "Travailler", translation: "To work", icon: "💼", pronunciation: "trah-vye-ay" },
  { verb: "Dîner", translation: "To dine", icon: "🍽️", pronunciation: "dee-nay" },
  { verb: "Chanter", translation: "To sing", icon: "🎤", pronunciation: "shon-tay" },
  { verb: "Jouer", translation: "To play", icon: "🎮", pronunciation: "joo-ay" },
];

const VISUAL_VOCAB_2 = [
  { verb: "Aimer", translation: "To like/love", icon: "❤️", pronunciation: "em-may" },
  { verb: "Dessiner", translation: "To draw", icon: "🎨", pronunciation: "deh-see-nay" },
  { verb: "Téléphoner", translation: "To call", icon: "📞", pronunciation: "tay-lay-fo-nay" },
  { verb: "Nager", translation: "To swim", icon: "🏊", pronunciation: "nah-jay" },
];

const MATCHING_PAIRS = [
  { id: "1", french: "Je regarde", english: "I watch" },
  { id: "2", french: "Tu danses", english: "You dance" },
  { id: "3", french: "Nous chantons", english: "We sing" },
  { id: "4", french: "Elle travaille", english: "She works" },
  { id: "5", french: "Ils mangent", english: "They eat" },
  { id: "6", french: "Vous habitez", english: "You (formal) live" },
];

const CONJUGATION_ITEMS = [
  { subject: "Je", verb: "parler", sentence: "[...] français.", answer: "parle", sentenceEn: "I [...] French." },
  { subject: "Tu", verb: "écouter", sentence: "[...] la musique.", answer: "écoutes", sentenceEn: "You [...] music." },
  { subject: "Nous", verb: "habiter", sentence: "[...] à Paris.", answer: "habitons", sentenceEn: "We [...] in Paris." },
  { subject: "Ils", verb: "manger", sentence: "[...] une pizza.", answer: "mangent", sentenceEn: "They [...] a pizza." },
  { subject: "Elle", verb: "jouer", sentence: "[...] au tennis.", answer: "joue", sentenceEn: "She [...] tennis." },
];

const UNSCRAMBLE_ITEMS = [
  { id: "u1", words: ["parle", "Je", "français"], correct: "Je parle français", translation: "I speak French" },
  { id: "u2", words: ["pas", "ne", "Il", "dîne"], correct: "Il ne dîne pas", translation: "He is not having dinner" },
  { id: "u3", words: ["aimons", "Nous", "voyager"], correct: "Nous aimons voyager", translation: "We love to travel" },
];

const ERROR_CORRECTION_ITEMS = [
  { id: "e1", incorrect: "Tu parle anglais ?", correct: "Tu parles anglais ?", explanation: 'With "Tu", you must add -S.', correctEn: "Do you speak English?" },
  { id: "e2", incorrect: "Nous mangons la pizza.", correct: "Nous mangeons la pizza.", explanation: 'Keep the "E" in -ger verbs with Nous.', correctEn: "We eat pizza." },
  { id: "e3", incorrect: "Ils danses bien.", correct: "Ils dansent bien.", explanation: "The plural ending is -ENT, not -ES.", correctEn: "They dance well." },
];

// Translation dictionary for clickable words
const WORD_TRANSLATIONS = {
  // Pronouns
  "je": "I", "j'": "I", "tu": "you", "il": "he", "elle": "she", "on": "one/we",
  "nous": "we", "vous": "you (formal/plural)", "ils": "they (m.)", "elles": "they (f.)",
  // Parler
  "parle": "speak(s)", "parles": "speak", "parlons": "speak", "parlez": "speak", "parlent": "speak", "parler": "to speak",
  // Écouter
  "écouter": "to listen", "écoute": "listen(s)", "écoutes": "listen",
  "écoutons": "we listen", "écoutez": "you listen (formal)", "écoutent": "they listen",
  // Habiter
  "habiter": "to live (somewhere)", "habite": "live(s)", "habites": "live", "habitons": "we live", "habitez": "you live", "habitent": "live",
  // Manger
  "manger": "to eat", "mange": "eat(s)", "manges": "eat", "mangeons": "we eat", "mangez": "you eat", "mangent": "they eat",
  // Jouer
  "jouer": "to play", "joue": "play(s)", "joues": "play", "jouons": "play", "jouez": "play", "jouent": "play",
  // Regarder
  "regarder": "to watch", "regarde": "watch(es)", "regardes": "watch", "regardons": "watch", "regardez": "watch", "regardent": "watch",
  // Danser
  "danser": "to dance", "danse": "dance(s)", "danses": "dance", "dansons": "dance", "dansez": "dance", "dansent": "they dance",
  // Chanter
  "chanter": "to sing", "chante": "sing(s)", "chantes": "sing", "chantons": "we sing", "chantez": "sing", "chantent": "sing",
  // Travailler
  "travailler": "to work", "travaille": "work(s)", "travailles": "work", "travaillons": "work", "travaillez": "work", "travaillent": "work",
  // Cuisiner
  "cuisiner": "to cook", "cuisine": "cook(s)", "cuisines": "cook", "cuisinons": "cook", "cuisinez": "cook", "cuisinent": "cook",
  // Étudier
  "étudier": "to study", "étudie": "study/studies", "étudies": "study", "étudions": "study", "étudiez": "study", "étudient": "study",
  // Voyager
  "voyager": "to travel", "voyage": "travel(s)", "voyages": "travel", "voyageons": "we travel", "voyagez": "travel", "voyagent": "travel",
  // Dîner
  "dîner": "to dine", "dîne": "dine(s)", "dînes": "dine", "dînons": "dine", "dînez": "dine", "dînent": "dine",
  // Aimer
  "aimer": "to like/love", "aime": "like(s)/love(s)", "aimes": "like", "aimons": "we like/love", "aimez": "like/love", "aiment": "like",
  // Dessiner, Nager, Téléphoner
  "dessiner": "to draw", "dessine": "draw(s)", "nager": "to swim", "nage": "swim(s)",
  "téléphoner": "to call", "téléphone": "call(s)",
  // Common words
  "français": "French", "anglais": "English", "la": "the (fem.)", "le": "the (masc.)", "les": "the (plural)",
  "musique": "music", "pizza": "pizza", "une": "a (fem.)", "un": "a (masc.)",
  "à": "in/at/to", "au": "at the", "paris": "Paris", "tennis": "tennis",
  "ne": "not (part 1)", "pas": "not (part 2)", "bien": "well/good",
  "est-ce": "is it that", "que": "that", "chocolat": "chocolate",
  "j'écoute": "I listen",
  // Stem slide
  "étudi-": "studi-", "mang-": "eat-", "chant-": "sing-", "habit-": "live-", "parl": "speak",
};

// Full sentence translations for when word-by-word doesn't work well
const SENTENCE_TRANSLATIONS = {
  "Est-ce que vous aimez le chocolat ?": "Do you like chocolate?",
  "Vous aimez le chocolat.": "You like chocolate.",
  "Je parle français.": "I speak French.",
  "Je ne parle pas français.": "I don't speak French.",
  "Nous écoutons la musique.": "We listen to music.",
  "J'écoute": "I listen",
  "Nous mangeons": "We eat",
  "Nous mangeons la pizza.": "We eat pizza.",
  "Nous mangons la pizza.": "(incorrect) We eat pizza.",
  "Tu parle anglais ?": "(incorrect) Do you speak English?",
  "Tu parles anglais ?": "Do you speak English?",
  "Ils danses bien.": "(incorrect) They dance well.",
  "Ils dansent bien.": "They dance well.",
  "Je parle français": "I speak French",
  "Il ne dîne pas": "He is not having dinner",
  "Nous aimons voyager": "We love to travel",
};

// ── PREMIUM VOICE ENGINE ──────────────────────────────────────
// Selects the best available French voice on the device

const VoiceEngine = {
  _ctx: null,
  _bestVoice: null,
  _voicesLoaded: false,

  getCtx() {
    if (!this._ctx) {
      this._ctx = new (window.AudioContext || window.webkitAudioContext)();
    }
    return this._ctx;
  },

  // Rank voices by quality — premium/enhanced voices first
  _rankVoice(v) {
    const name = v.name.toLowerCase();
    // Google premium voices (Chrome)
    if (name.includes("google") && name.includes("fr")) return 100;
    // Apple premium voices (Safari)
    if (name.includes("thomas") || name.includes("amelie") || name.includes("audrey")) return 95;
    // Microsoft premium
    if (name.includes("denise") || name.includes("henri") || name.includes("vivienne")) return 90;
    // Any "enhanced" or "premium" label
    if (name.includes("enhanced") || name.includes("premium") || name.includes("natural")) return 85;
    // Any French voice
    if (v.lang && v.lang.startsWith("fr")) return 50;
    return 0;
  },

  loadBestVoice() {
    if (!("speechSynthesis" in window)) return;
    const tryLoad = () => {
      const voices = window.speechSynthesis.getVoices();
      const frenchVoices = voices.filter(
        (v) => v.lang && (v.lang.startsWith("fr") || v.name.toLowerCase().includes("french"))
      );
      if (frenchVoices.length > 0) {
        frenchVoices.sort((a, b) => this._rankVoice(b) - this._rankVoice(a));
        this._bestVoice = frenchVoices[0];
        this._voicesLoaded = true;
      }
    };
    tryLoad();
    if (!this._voicesLoaded) {
      window.speechSynthesis.onvoiceschanged = tryLoad;
    }
  },

  speak(text, rate = 0.82) {
    if (!("speechSynthesis" in window)) return;
    window.speechSynthesis.cancel();
    const u = new SpeechSynthesisUtterance(text);
    u.lang = "fr-FR";
    u.rate = rate;
    u.pitch = 1.02;
    u.volume = 1;
    if (this._bestVoice) u.voice = this._bestVoice;
    window.speechSynthesis.speak(u);
  },

  // Sound effects via Web Audio API
  sfx(type) {
    try {
      const ctx = this.getCtx();
      const now = ctx.currentTime;

      if (type === "click") {
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain); gain.connect(ctx.destination);
        osc.type = "sine";
        osc.frequency.setValueAtTime(880, now);
        osc.frequency.exponentialRampToValueAtTime(440, now + 0.06);
        gain.gain.setValueAtTime(0.06, now);
        gain.gain.exponentialRampToValueAtTime(0.001, now + 0.06);
        osc.start(now); osc.stop(now + 0.06);
      } else if (type === "success") {
        [523, 659, 784].forEach((freq, i) => {
          const o = ctx.createOscillator();
          const g = ctx.createGain();
          o.connect(g); g.connect(ctx.destination);
          o.type = "triangle";
          o.frequency.setValueAtTime(freq, now + i * 0.08);
          g.gain.setValueAtTime(0.08, now + i * 0.08);
          g.gain.linearRampToValueAtTime(0, now + i * 0.08 + 0.3);
          o.start(now + i * 0.08); o.stop(now + i * 0.08 + 0.3);
        });
      } else if (type === "error") {
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain); gain.connect(ctx.destination);
        osc.type = "sawtooth";
        osc.frequency.setValueAtTime(180, now);
        osc.frequency.linearRampToValueAtTime(90, now + 0.25);
        gain.gain.setValueAtTime(0.06, now);
        gain.gain.linearRampToValueAtTime(0, now + 0.25);
        osc.start(now); osc.stop(now + 0.25);
      } else if (type === "unlock") {
        [400, 500, 650, 800, 1000, 1200].forEach((freq, i) => {
          const o = ctx.createOscillator();
          const g = ctx.createGain();
          o.connect(g); g.connect(ctx.destination);
          o.type = "sine";
          o.frequency.setValueAtTime(freq, now + i * 0.06);
          g.gain.setValueAtTime(0.1, now + i * 0.06);
          g.gain.linearRampToValueAtTime(0, now + i * 0.06 + 0.35);
          o.start(now + i * 0.06); o.stop(now + i * 0.06 + 0.35);
        });
      } else if (type === "levelup") {
        [523, 659, 784, 1047].forEach((freq, i) => {
          const o = ctx.createOscillator();
          const g = ctx.createGain();
          o.connect(g); g.connect(ctx.destination);
          o.type = "sine";
          o.frequency.setValueAtTime(freq, now + i * 0.12);
          g.gain.setValueAtTime(0.1, now + i * 0.12);
          g.gain.linearRampToValueAtTime(0, now + i * 0.12 + 0.5);
          o.start(now + i * 0.12); o.stop(now + i * 0.12 + 0.5);
        });
      } else if (type === "hover") {
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain); gain.connect(ctx.destination);
        osc.type = "sine";
        osc.frequency.setValueAtTime(600, now);
        gain.gain.setValueAtTime(0.012, now);
        gain.gain.linearRampToValueAtTime(0, now + 0.04);
        osc.start(now); osc.stop(now + 0.04);
      }
    } catch (e) {}
  },
};

// ── CLICKABLE FRENCH WORD (shows English on click) ────────────

const ClickWord = ({ word, style: extraStyle = {} }) => {
  const [showTrans, setShowTrans] = useState(false);
  const timeoutRef = useRef(null);

  const cleanWord = word.replace(/[.,?!;:]/g, "").toLowerCase().trim();
  const punctuation = word.match(/[.,?!;:]$/)?.[0] || "";
  const trans = WORD_TRANSLATIONS[cleanWord];

  const handleClick = (e) => {
    e.stopPropagation();
    if (!trans) return;
    VoiceEngine.sfx("click");
    VoiceEngine.speak(word.replace(/[.,?!;:]/g, ""), 0.75);
    setShowTrans(true);
    if (timeoutRef.current) clearTimeout(timeoutRef.current);
    timeoutRef.current = setTimeout(() => setShowTrans(false), 2200);
  };

  if (!trans) return <span style={extraStyle}>{word}</span>;

  return (
    <span
      onClick={handleClick}
      style={{
        position: "relative",
        cursor: "pointer",
        borderBottom: "1px dotted rgba(99,102,241,0.3)",
        transition: "all 0.15s",
        ...extraStyle,
      }}
    >
      {word.replace(/[.,?!;:]$/, "")}
      {punctuation}
      {showTrans && (
        <span
          style={{
            position: "absolute",
            bottom: "calc(100% + 6px)",
            left: "50%",
            transform: "translateX(-50%)",
            background: "#0f172a",
            color: "#e0f2fe",
            padding: "5px 12px",
            borderRadius: 8,
            fontSize: 11,
            fontWeight: 700,
            whiteSpace: "nowrap",
            zIndex: 999,
            boxShadow: "0 4px 16px rgba(0,0,0,0.3)",
            animation: "tooltipIn 0.15s ease-out",
            fontFamily: "'DM Sans', sans-serif",
            letterSpacing: 0.3,
            pointerEvents: "none",
          }}
        >
          {trans}
          <span
            style={{
              position: "absolute",
              top: "100%",
              left: "50%",
              transform: "translateX(-50%)",
              width: 0,
              height: 0,
              borderLeft: "5px solid transparent",
              borderRight: "5px solid transparent",
              borderTop: "5px solid #0f172a",
            }}
          />
        </span>
      )}
    </span>
  );
};

// Helper: render a French sentence with clickable words + optional sentence translation
const ClickableSentence = ({ text, style: extraStyle = {}, showSentenceHint = false }) => {
  const [showFull, setShowFull] = useState(false);
  const words = text.split(/(\s+)/);
  const sentenceTrans = SENTENCE_TRANSLATIONS[text] || SENTENCE_TRANSLATIONS[text.replace(/\s+/g, " ").trim()];

  return (
    <span style={{ ...extraStyle, position: "relative" }}>
      {words.map((w, i) =>
        w.trim() === "" ? (
          <span key={i}>{w}</span>
        ) : (
          <ClickWord key={i} word={w} />
        )
      )}
      {showSentenceHint && sentenceTrans && (
        <>
          <button onClick={(e) => { e.stopPropagation(); setShowFull(!showFull); }}
            style={{ background: "none", border: "none", cursor: "pointer", fontSize: 10, color: "#94a3b8", marginLeft: 4, verticalAlign: "middle" }}
          >💬</button>
          {showFull && (
            <span style={{
              display: "block", fontSize: 11, color: "#64748b", fontStyle: "italic",
              fontFamily: "'DM Sans', sans-serif", marginTop: 4, fontWeight: 400,
            }}>
              = "{sentenceTrans}"
            </span>
          )}
        </>
      )}
    </span>
  );
};

// ── TOAST ─────────────────────────────────────────────────────

const Toast = ({ message, type }) => {
  if (!message) return null;
  const bg = type === "success" ? "#059669" : type === "error" ? "#dc2626" : "#4f46e5";
  return (
    <div
      style={{
        position: "fixed",
        bottom: 36,
        left: "50%",
        transform: "translateX(-50%)",
        background: bg,
        color: "#fff",
        padding: "12px 28px",
        borderRadius: 50,
        fontWeight: 800,
        fontSize: 14,
        zIndex: 9999,
        boxShadow: `0 8px 28px ${bg}66`,
        animation: "tooltipIn 0.2s ease-out",
        letterSpacing: 0.5,
        fontFamily: "'DM Sans', sans-serif",
      }}
    >
      {message}
    </div>
  );
};

// ── SECTION LAYOUT ────────────────────────────────────────────

const SectionLayout = ({ children, title, index, isLocked, id }) => (
  <section
    id={id}
    style={{
      minHeight: "100vh",
      width: "100%",
      display: "flex",
      flexDirection: "column",
      alignItems: "center",
      justifyContent: "center",
      padding: "60px 16px",
      position: "relative",
      transition: "all 0.7s",
      filter: isLocked ? "grayscale(1) brightness(0.35)" : "none",
    }}
  >
    <div
      style={{
        width: "100%",
        maxWidth: 920,
        transition: "all 0.8s cubic-bezier(0.16, 1, 0.3, 1)",
        transform: isLocked ? "scale(0.94)" : "scale(1)",
        opacity: isLocked ? 0.35 : 1,
        pointerEvents: isLocked ? "none" : "auto",
      }}
    >
      <div
        style={{
          borderRadius: 28,
          overflow: "hidden",
          background: isLocked ? "rgba(10,15,30,0.85)" : "rgba(255,255,255,0.96)",
          backdropFilter: "blur(24px)",
          border: isLocked ? "2px solid rgba(40,50,80,0.4)" : "2px solid rgba(226,232,240,0.6)",
          boxShadow: isLocked ? "none" : "0 24px 64px rgba(0,0,0,0.08), 0 0 0 1px rgba(0,0,0,0.03)",
        }}
      >
        <header
          style={{
            display: "flex",
            alignItems: "center",
            gap: 14,
            padding: "22px 28px",
            borderBottom: `1px solid ${isLocked ? "rgba(40,50,80,0.3)" : "#f1f5f9"}`,
          }}
        >
          <div
            style={{
              width: 42,
              height: 42,
              borderRadius: 12,
              background: isLocked ? "#1e293b" : "linear-gradient(135deg, #0ea5e9, #6366f1)",
              display: "flex",
              alignItems: "center",
              justifyContent: "center",
              color: "#fff",
              fontSize: 18,
              boxShadow: isLocked ? "none" : "0 4px 12px rgba(14,165,233,0.3)",
            }}
          >
            {isLocked ? "🔒" : "🔓"}
          </div>
          <div>
            <h2
              style={{
                margin: 0,
                fontSize: 19,
                fontWeight: 800,
                textTransform: "uppercase",
                letterSpacing: 0.5,
                color: isLocked ? "#475569" : "#0f172a",
                fontFamily: "'Outfit', sans-serif",
              }}
            >
              {title}
            </h2>
            <div style={{ display: "flex", alignItems: "center", gap: 8, marginTop: 3 }}>
              <span
                style={{
                  fontSize: 9,
                  fontWeight: 800,
                  padding: "2px 7px",
                  borderRadius: 4,
                  color: "#fff",
                  background: isLocked ? "#334155" : "#0ea5e9",
                  letterSpacing: 0.5,
                }}
              >
                LVL {index}
              </span>
              <span
                style={{
                  fontSize: 9,
                  fontWeight: 700,
                  letterSpacing: 2,
                  textTransform: "uppercase",
                  color: "#94a3b8",
                  fontFamily: "'JetBrains Mono', monospace",
                }}
              >
                {isLocked ? "Locked" : "Active"}
              </span>
            </div>
          </div>
          {!isLocked && (
            <div style={{ marginLeft: "auto" }}>
              <div
                style={{
                  width: 8,
                  height: 8,
                  borderRadius: "50%",
                  background: "#10b981",
                  boxShadow: "0 0 10px rgba(16,185,129,0.7)",
                  animation: "pulse 2s infinite",
                }}
              />
            </div>
          )}
        </header>
        <div style={{ padding: "28px 28px 36px" }}>{children}</div>
      </div>
    </div>

    {isLocked && (
      <div
        style={{
          position: "absolute",
          inset: 0,
          display: "flex",
          alignItems: "center",
          justifyContent: "center",
          zIndex: 20,
        }}
      >
        <div
          style={{
            background: "rgba(8,12,25,0.92)",
            backdropFilter: "blur(16px)",
            padding: "44px 40px",
            borderRadius: 24,
            textAlign: "center",
            border: "1px solid #1e293b",
            maxWidth: 380,
            boxShadow: "0 20px 60px rgba(0,0,0,0.5)",
          }}
        >
          <div
            style={{
              width: 64,
              height: 64,
              background: "#0f172a",
              borderRadius: "50%",
              display: "flex",
              alignItems: "center",
              justifyContent: "center",
              margin: "0 auto 20px",
              fontSize: 28,
              border: "2px solid #1e293b",
            }}
          >
            🔒
          </div>
          <h3
            style={{
              color: "#fff",
              fontSize: 18,
              fontWeight: 800,
              margin: "0 0 6px",
              fontFamily: "'Outfit', sans-serif",
            }}
          >
            Security Protocol
          </h3>
          <p style={{ color: "#475569", margin: 0, fontSize: 13 }}>
            Complete the previous chamber to decrypt this level.
          </p>
        </div>
      </div>
    )}
  </section>
);

// ── COVER ─────────────────────────────────────────────────────

const CoverSlide = ({ onStart }) => (
  <section
    style={{
      minHeight: "100vh",
      width: "100%",
      display: "flex",
      flexDirection: "column",
      justifyContent: "center",
      alignItems: "center",
      padding: 32,
      position: "relative",
      overflow: "hidden",
      color: "#fff",
    }}
  >
    <div
      style={{
        position: "absolute",
        inset: 0,
        background: "linear-gradient(160deg, #020617 0%, #0c1222 30%, #0a0f1e 60%, #020617 100%)",
      }}
    />
    {/* Cyan glow top-right */}
    <div style={{
      position: "absolute", top: -150, right: -150, width: 500, height: 500, borderRadius: "50%",
      background: "radial-gradient(circle, rgba(14,165,233,0.18) 0%, transparent 65%)", filter: "blur(50px)",
    }} />
    {/* Warm glow bottom-left */}
    <div style={{
      position: "absolute", bottom: -150, left: -100, width: 450, height: 450, borderRadius: "50%",
      background: "radial-gradient(circle, rgba(245,158,11,0.12) 0%, transparent 65%)", filter: "blur(50px)",
    }} />
    {/* Scanline overlay */}
    <div style={{
      position: "absolute", inset: 0, opacity: 0.03, pointerEvents: "none",
      backgroundImage: "repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(255,255,255,0.03) 2px, rgba(255,255,255,0.03) 4px)",
    }} />

    <div style={{ position: "relative", zIndex: 10, textAlign: "center", maxWidth: 680 }}>
      <div
        style={{
          display: "inline-flex",
          alignItems: "center",
          gap: 10,
          background: "rgba(255,255,255,0.04)",
          backdropFilter: "blur(8px)",
          padding: "7px 20px",
          borderRadius: 50,
          border: "1px solid rgba(255,255,255,0.06)",
          marginBottom: 36,
          animation: "fadeIn 0.8s ease-out",
        }}
      >
        <div style={{ width: 7, height: 7, borderRadius: "50%", background: "#34d399", animation: "pulse 2s infinite" }} />
        <span style={{
          textTransform: "uppercase", letterSpacing: 4, fontSize: 10, fontWeight: 700,
          color: "rgba(186,230,253,0.8)", fontFamily: "'JetBrains Mono', monospace",
        }}>
          System Online
        </span>
      </div>

      <h1
        style={{
          fontSize: "clamp(52px, 11vw, 110px)",
          fontWeight: 900,
          lineHeight: 0.88,
          margin: "0 0 12px",
          fontFamily: "'Outfit', sans-serif",
          animation: "fadeIn 0.8s ease-out 0.15s both",
        }}
      >
        <span style={{
          background: "linear-gradient(135deg, #7dd3fc 0%, #38bdf8 30%, #0ea5e9 60%, #818cf8 100%)",
          WebkitBackgroundClip: "text", WebkitTextFillColor: "transparent",
        }}>
          ESCAPE
        </span>
        <br />
        <span style={{ color: "#f1f5f9", letterSpacing: -3 }}>FLAB</span>
      </h1>

      {/* Subtitle: -ER verbs au présent */}
      <div style={{
        display: "flex", alignItems: "center", justifyContent: "center", gap: 12, marginBottom: 12,
        animation: "fadeIn 0.8s ease-out 0.3s both",
      }}>
        <div style={{ height: 1, width: 40, background: "rgba(14,165,233,0.3)" }} />
        <p style={{
          fontSize: "clamp(14px, 2.5vw, 22px)", fontWeight: 800,
          color: "#7dd3fc", letterSpacing: 4,
          fontFamily: "'JetBrains Mono', monospace", margin: 0,
        }}>
          -ER VERBS • PRÉSENT
        </p>
        <div style={{ height: 1, width: 40, background: "rgba(14,165,233,0.3)" }} />
      </div>

      <div style={{
        display: "inline-flex", alignItems: "center", gap: 8,
        background: "rgba(14,165,233,0.08)", border: "1px solid rgba(14,165,233,0.15)",
        padding: "5px 16px", borderRadius: 50, marginBottom: 40,
        animation: "fadeIn 0.8s ease-out 0.4s both",
      }}>
        <span style={{ fontSize: 11, fontWeight: 700, color: "#38bdf8", letterSpacing: 2, fontFamily: "'JetBrains Mono', monospace" }}>
          LEVEL A1.1.1
        </span>
      </div>

      <p style={{
        fontSize: 15, color: "#64748b", maxWidth: 480, margin: "0 auto 44px", lineHeight: 1.75,
        animation: "fadeIn 0.8s ease-out 0.5s both", fontFamily: "'DM Sans', sans-serif",
      }}>
        Mission: Infiltrate the archive, master the -ER verb codes, and unlock the exit before time runs out.
      </p>

      <div style={{ animation: "fadeIn 0.8s ease-out 0.65s both" }}>
        <button
          onClick={() => { VoiceEngine.sfx("unlock"); onStart(); }}
          onMouseEnter={() => VoiceEngine.sfx("hover")}
          style={{
            background: "linear-gradient(135deg, #0ea5e9, #6366f1)",
            color: "#fff", border: "none",
            padding: "18px 44px", borderRadius: 16,
            fontSize: 16, fontWeight: 800, cursor: "pointer",
            boxShadow: "0 0 40px rgba(14,165,233,0.25), 0 4px 20px rgba(99,102,241,0.2)",
            transition: "all 0.25s", fontFamily: "'Outfit', sans-serif", letterSpacing: 1,
          }}
        >
          INITIALIZE MISSION ⬇
        </button>
      </div>

      <p style={{
        marginTop: 28, fontSize: 11, color: "#334155",
        fontFamily: "'JetBrains Mono', monospace", letterSpacing: 1,
        animation: "fadeIn 0.8s ease-out 0.8s both",
      }}>
        💡 Tap any French word to see its English translation
      </p>
    </div>
  </section>
);

// ── BRIEFING ──────────────────────────────────────────────────

const LessonPlanSlide = ({ onUnlock }) => (
  <div style={{ textAlign: "center" }}>
    <div style={{
      width: 80, height: 80, borderRadius: "50%",
      background: "linear-gradient(135deg, #e0f2fe, #dbeafe)",
      display: "flex", alignItems: "center", justifyContent: "center",
      margin: "0 auto 28px", fontSize: 40, animation: "bounceIn 0.5s",
    }}>
      ⭐
    </div>
    <h3 style={{ fontSize: 24, fontWeight: 900, color: "#0f172a", marginBottom: 10, fontFamily: "'Outfit', sans-serif" }}>
      MISSION BRIEFING
    </h3>
    <p style={{ color: "#64748b", fontSize: 15, maxWidth: 520, margin: "0 auto 36px", lineHeight: 1.7, fontFamily: "'DM Sans', sans-serif" }}>
      You are trapped in the conjugation simulator. To escape, navigate through security chambers. Each chamber is protected by a linguistic puzzle.
    </p>
    <div style={{ display: "grid", gridTemplateColumns: "repeat(3, 1fr)", gap: 14, marginBottom: 36 }}>
      {["Observe", "Decide", "Conjugate"].map((txt, i) => (
        <div key={i} style={{ background: "#f8fafc", padding: 20, borderRadius: 16, border: "1px solid #f1f5f9", textAlign: "center" }}>
          <div style={{ fontSize: 28, fontWeight: 900, color: "#e2e8f0", fontFamily: "'JetBrains Mono', monospace" }}>{i + 1}</div>
          <div style={{ fontWeight: 700, color: "#475569", textTransform: "uppercase", fontSize: 12, letterSpacing: 1 }}>{txt}</div>
        </div>
      ))}
    </div>
    <button
      onClick={() => { VoiceEngine.sfx("success"); onUnlock(); }}
      style={{
        background: "#0f172a", color: "#fff", border: "none",
        padding: "14px 36px", borderRadius: 12, fontSize: 15, fontWeight: 800,
        cursor: "pointer", boxShadow: "0 6px 20px rgba(0,0,0,0.2)",
        fontFamily: "'Outfit', sans-serif", letterSpacing: 1,
      }}
    >
      START SIMULATION
    </button>
  </div>
);

// ── VISUAL VOCAB 1 ────────────────────────────────────────────

const VisualVocabSlide = ({ onUnlock }) => {
  const [selectedIcon, setSelectedIcon] = useState(null); // verb name from icon click
  const [selectedWord, setSelectedWord] = useState(null); // verb name from word click
  const [matches, setMatches] = useState({});
  const [feedback, setFeedback] = useState(null);

  useEffect(() => {
    if (Object.keys(matches).length === VISUAL_VOCAB.length) {
      VoiceEngine.sfx("unlock");
      setTimeout(onUnlock, 1200);
    }
  }, [matches]);

  const tryMatch = (iconVerb, wordVerb) => {
    if (iconVerb === wordVerb) {
      VoiceEngine.sfx("success");
      setMatches((p) => ({ ...p, [iconVerb]: true }));
      setSelectedIcon(null);
      setSelectedWord(null);
      setFeedback("Correct!");
      setTimeout(() => setFeedback(null), 1000);
    } else {
      VoiceEngine.sfx("error");
      setSelectedIcon(null);
      setSelectedWord(null);
      setFeedback("Try again!");
      setTimeout(() => setFeedback(null), 1000);
    }
  };

  const handleIconClick = (verb) => {
    if (matches[verb]) return;
    VoiceEngine.sfx("click");
    VoiceEngine.speak(verb);
    if (selectedWord) {
      // A word is already selected — try to match
      tryMatch(verb, selectedWord);
    } else {
      // Select this icon, wait for word click
      setSelectedIcon(verb);
    }
  };

  const handleWordClick = (verbName) => {
    if (matches[verbName]) return;
    VoiceEngine.sfx("click");
    VoiceEngine.speak(verbName);
    if (selectedIcon) {
      // An icon is already selected — try to match
      tryMatch(selectedIcon, verbName);
    } else {
      // Select this word, wait for icon click
      setSelectedWord(verbName);
    }
  };

  return (
    <>
      <p style={{ textAlign: "center", color: "#64748b", marginBottom: 20, fontFamily: "'DM Sans', sans-serif", fontSize: 14 }}>
        Match icons to verbs — click either side first. <span style={{ color: "#0ea5e9", fontWeight: 700 }}>Click to listen.</span>
      </p>
      <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill, minmax(90px, 1fr))", gap: 10, marginBottom: 28 }}>
        {VISUAL_VOCAB.map((item) => {
          const isMatched = !!matches[item.verb];
          const isSel = selectedIcon === item.verb;
          return (
            <button key={item.verb} onClick={() => handleIconClick(item.verb)} disabled={isMatched}
              style={{
                height: 100, borderRadius: 16,
                border: isSel ? "2px solid #0ea5e9" : isMatched ? "2px solid #6ee7b7" : "1px solid #f1f5f9",
                background: isSel ? "linear-gradient(135deg, #0ea5e9, #6366f1)" : isMatched ? "#f0fdf4" : "#fff",
                cursor: isMatched ? "default" : "pointer",
                display: "flex", flexDirection: "column", alignItems: "center", justifyContent: "center", gap: 4,
                transition: "all 0.2s",
                transform: isSel ? "scale(1.06)" : "scale(1)",
                boxShadow: isSel ? "0 6px 20px rgba(14,165,233,0.25)" : "0 1px 3px rgba(0,0,0,0.04)",
                position: "relative",
              }}
            >
              <span style={{ fontSize: 24 }}>{item.icon}</span>
              {isMatched && (
                <div style={{ animation: "fadeIn 0.2s" }}>
                  <div style={{ fontSize: 8, fontWeight: 800, textTransform: "uppercase", color: "#059669" }}>{item.verb}</div>
                  <div style={{ fontSize: 7, fontFamily: "'JetBrains Mono', monospace", color: "#34d399" }}>/{item.pronunciation}/</div>
                </div>
              )}
              {!isMatched && <span style={{ position: "absolute", top: 4, right: 6, fontSize: 8, opacity: 0.25 }}>🔊</span>}
            </button>
          );
        })}
      </div>
      <div style={{ display: "flex", flexWrap: "wrap", justifyContent: "center", gap: 8, minHeight: 44 }}>
        {VISUAL_VOCAB.filter((v) => !matches[v.verb]).map((item) => (
          <button key={item.verb} onClick={() => handleWordClick(item.verb)}
            style={{
              padding: "8px 16px", border: "none",
              background: selectedWord === item.verb ? "linear-gradient(135deg, #0ea5e9, #6366f1)" : "#0f172a",
              color: "#fff",
              borderRadius: 10, fontWeight: 800, fontSize: 10, letterSpacing: 1.5,
              textTransform: "uppercase", cursor: "pointer", fontFamily: "'Outfit', sans-serif",
              boxShadow: selectedWord === item.verb ? "0 6px 20px rgba(14,165,233,0.25)" : "0 3px 10px rgba(0,0,0,0.15)",
              transform: selectedWord === item.verb ? "scale(1.06)" : "scale(1)",
              transition: "all 0.2s",
              display: "flex", flexDirection: "column", alignItems: "center",
            }}
          >
            {item.verb}
            <span style={{ fontSize: 7, opacity: 0.4, fontFamily: "'JetBrains Mono', monospace", marginTop: 1 }}>/{item.pronunciation}/</span>
          </button>
        ))}
      </div>
      <Toast message={feedback} type={feedback === "Correct!" ? "success" : "error"} />
    </>
  );
};

// ── STEM SLIDE ────────────────────────────────────────────────

const DefinitionSlide = ({ onUnlock }) => {
  const STEMS = [
    { verb: "Parler", stem: "parl", en: "to speak", hint: "Remove -ER" },
    { verb: "Étudier", stem: "étudi", en: "to study", hint: "Remove -ER" },
    { verb: "Manger", stem: "mang", en: "to eat", hint: "Remove -ER" },
    { verb: "Chanter", stem: "chant", en: "to sing", hint: "Remove -ER" },
    { verb: "Habiter", stem: "habit", en: "to live", hint: "Remove -ER" },
  ];

  const [currentIdx, setCurrentIdx] = useState(0);
  const [input, setInput] = useState("");
  const [status, setStatus] = useState("idle"); // idle | correct | wrong
  const [completed, setCompleted] = useState(new Set());
  const [showTip, setShowTip] = useState(true);

  const current = STEMS[currentIdx];

  const handleSubmit = () => {
    if (input.toLowerCase().trim() === current.stem) {
      VoiceEngine.sfx("success");
      VoiceEngine.speak(current.stem);
      setStatus("correct");
      const nc = new Set(completed);
      nc.add(currentIdx);
      setCompleted(nc);

      setTimeout(() => {
        if (nc.size === STEMS.length) {
          VoiceEngine.sfx("unlock");
          setTimeout(onUnlock, 800);
        } else {
          // Move to next unsolved
          let next = (currentIdx + 1) % STEMS.length;
          while (nc.has(next)) next = (next + 1) % STEMS.length;
          setCurrentIdx(next);
          setInput("");
          setStatus("idle");
          setShowTip(false);
        }
      }, 1000);
    } else {
      VoiceEngine.sfx("error");
      setStatus("wrong");
      setTimeout(() => setStatus("idle"), 1200);
    }
  };

  return (
    <div style={{ textAlign: "center" }}>
      {/* Tip box - shown on first verb */}
      {showTip && (
        <div style={{
          background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 14, padding: "14px 20px",
          marginBottom: 24, textAlign: "left", maxWidth: 500, margin: "0 auto 24px",
        }}>
          <p style={{ margin: 0, fontSize: 13, color: "#0369a1", fontFamily: "'DM Sans', sans-serif", lineHeight: 1.6 }}>
            💡 <strong>TIP:</strong> To conjugate an -ER verb, first find the <strong>stem</strong> (le radical).
            Remove the <strong>-ER</strong> ending from the infinitive. Example: <strong>Parler → Parl</strong>
          </p>
        </div>
      )}

      {/* Progress dots */}
      <div style={{ display: "flex", justifyContent: "center", gap: 8, marginBottom: 24 }}>
        {STEMS.map((s, i) => (
          <div key={i}
            onClick={() => { if (!completed.has(i)) { setCurrentIdx(i); setInput(""); setStatus("idle"); } }}
            style={{
              width: 36, height: 36, borderRadius: 10, display: "flex", alignItems: "center", justifyContent: "center",
              fontSize: 11, fontWeight: 800, cursor: completed.has(i) ? "default" : "pointer",
              background: completed.has(i) ? "#dcfce7" : i === currentIdx ? "#0ea5e9" : "#f1f5f9",
              color: completed.has(i) ? "#059669" : i === currentIdx ? "#fff" : "#94a3b8",
              border: i === currentIdx && !completed.has(i) ? "2px solid #0ea5e9" : "1px solid transparent",
              transition: "all 0.2s",
            }}
          >
            {completed.has(i) ? "✓" : i + 1}
          </div>
        ))}
      </div>

      {/* Main verb card */}
      <div style={{
        background: "linear-gradient(135deg, #0c4a6e, #0f172a)", borderRadius: 24, padding: "40px 32px",
        maxWidth: 480, margin: "0 auto 24px", color: "#fff",
        boxShadow: "0 16px 40px rgba(14,165,233,0.2)",
      }}>
        <div style={{ fontSize: 11, color: "#64748b", letterSpacing: 2, textTransform: "uppercase", fontFamily: "'JetBrains Mono', monospace", marginBottom: 8 }}>
          Isolate the stem of:
        </div>
        <div style={{ fontSize: "clamp(36px, 7vw, 56px)", fontWeight: 900, fontFamily: "'Outfit', sans-serif", marginBottom: 4 }}>
          {current.verb}
          <button onClick={() => VoiceEngine.speak(current.verb)} style={{ background: "none", border: "none", cursor: "pointer", fontSize: 20, marginLeft: 8, verticalAlign: "middle" }}>🔊</button>
        </div>
        <div style={{ fontSize: 14, color: "#7dd3fc", fontStyle: "italic", marginBottom: 24 }}>({current.en})</div>

        <div style={{ display: "flex", alignItems: "center", gap: 8, justifyContent: "center" }}>
          <input
            type="text"
            value={input}
            onChange={(e) => { setInput(e.target.value); setStatus("idle"); }}
            onKeyDown={(e) => e.key === "Enter" && handleSubmit()}
            placeholder="Type the stem..."
            style={{
              padding: "12px 20px", fontSize: 22, fontWeight: 800, fontFamily: "'Outfit', sans-serif",
              textAlign: "center", background: "rgba(255,255,255,0.1)", border: "none",
              borderBottom: `3px solid ${status === "correct" ? "#22c55e" : status === "wrong" ? "#ef4444" : "#38bdf8"}`,
              color: "#fff", borderRadius: "8px 8px 0 0", outline: "none", width: 200,
              transition: "all 0.2s",
            }}
          />
          <button onClick={handleSubmit}
            style={{
              padding: "12px 24px", background: "#0ea5e9", color: "#fff", border: "none",
              borderRadius: 10, fontWeight: 800, cursor: "pointer", fontSize: 14,
              fontFamily: "'Outfit', sans-serif",
            }}
          >
            CHECK
          </button>
        </div>

        {status === "correct" && (
          <div style={{ marginTop: 14, color: "#4ade80", fontWeight: 800, animation: "bounceIn 0.3s", fontSize: 14 }}>
            ✅ {current.verb} → {current.stem}- (stem acquired!)
          </div>
        )}
        {status === "wrong" && (
          <div style={{ marginTop: 14, color: "#fca5a5", fontSize: 13, animation: "fadeIn 0.2s" }}>
            ❌ Not quite. Remember: remove <strong>-ER</strong> from the end.
          </div>
        )}
      </div>

      <p style={{ color: "#94a3b8", fontSize: 12, fontFamily: "'DM Sans', sans-serif" }}>
        {completed.size} / {STEMS.length} stems isolated
      </p>
    </div>
  );
};

// ── ENDINGS SLIDE ─────────────────────────────────────────────

const EndingsSlide = ({ onUnlock }) => {
  const VERB_EXAMPLES = {
    "Je": [{ v: "parle", full: "Je parle" }, { v: "chante", full: "Je chante" }, { v: "mange", full: "Je mange" }],
    "Tu": [{ v: "parles", full: "Tu parles" }, { v: "chantes", full: "Tu chantes" }, { v: "manges", full: "Tu manges" }],
    "Il / Elle / On": [{ v: "parle", full: "Il parle" }, { v: "chante", full: "Elle chante" }, { v: "mange", full: "On mange" }],
    "Nous": [{ v: "parlons", full: "Nous parlons" }, { v: "chantons", full: "Nous chantons" }, { v: "mangeons", full: "Nous mangeons" }],
    "Vous": [{ v: "parlez", full: "Vous parlez" }, { v: "chantez", full: "Vous chantez" }, { v: "mangez", full: "Vous mangez" }],
    "Ils / Elles": [{ v: "parlent", full: "Ils parlent" }, { v: "chantent", full: "Elles chantent" }, { v: "mangent", full: "Ils mangent" }],
  };

  const [phase, setPhase] = useState("learn"); // learn | quiz
  const [activeEnding, setActiveEnding] = useState(null);
  const [viewed, setViewed] = useState(new Set());
  // Quiz state
  const QUIZ = [
    { q: "Je + parler = ?", options: ["parle", "parles", "parlons", "parlent"], answer: "parle", subject: "Je" },
    { q: "Nous + chanter = ?", options: ["chante", "chantons", "chantez", "chantent"], answer: "chantons", subject: "Nous" },
    { q: "Tu + manger = ?", options: ["mange", "manges", "mangeons", "mangent"], answer: "manges", subject: "Tu" },
    { q: "Ils + habiter = ?", options: ["habite", "habites", "habitez", "habitent"], answer: "habitent", subject: "Ils" },
    { q: "Vous + écouter = ?", options: ["écoute", "écoutons", "écoutez", "écoutent"], answer: "écoutez", subject: "Vous" },
    { q: "Elle + jouer = ?", options: ["joue", "joues", "jouons", "jouent"], answer: "joue", subject: "Elle" },
  ];
  const [quizIdx, setQuizIdx] = useState(0);
  const [quizStatus, setQuizStatus] = useState("idle");
  const [quizScore, setQuizScore] = useState(0);

  const handleLearnClick = (i, e) => {
    VoiceEngine.sfx("click");
    VoiceEngine.speak(VERB_EXAMPLES[e.subject][0].full);
    setActiveEnding(i);
    const nv = new Set(viewed); nv.add(i); setViewed(nv);
  };

  const startQuiz = () => {
    VoiceEngine.sfx("click");
    setPhase("quiz");
    setQuizIdx(0);
    setQuizScore(0);
    setQuizStatus("idle");
  };

  const handleQuizAnswer = (answer) => {
    VoiceEngine.sfx("click");
    const correct = QUIZ[quizIdx].answer;
    if (answer === correct) {
      VoiceEngine.sfx("success");
      VoiceEngine.speak(QUIZ[quizIdx].subject + " " + correct);
      setQuizStatus("correct");
      setQuizScore((s) => s + 1);
      setTimeout(() => {
        if (quizIdx < QUIZ.length - 1) {
          setQuizIdx((i) => i + 1);
          setQuizStatus("idle");
        } else {
          VoiceEngine.sfx("unlock");
          setTimeout(onUnlock, 800);
        }
      }, 1000);
    } else {
      VoiceEngine.sfx("error");
      setQuizStatus("wrong");
      setTimeout(() => setQuizStatus("idle"), 1200);
    }
  };

  if (phase === "learn") {
    return (
      <>
        <div style={{ background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 14, padding: "12px 18px", marginBottom: 20, textAlign: "left" }}>
          <p style={{ margin: 0, fontSize: 12, color: "#0369a1", fontFamily: "'DM Sans', sans-serif", lineHeight: 1.6 }}>
            💡 <strong>TIP:</strong> Each subject pronoun gets a specific ending added to the stem. Study all 6 patterns below, then pass the quiz to proceed.
          </p>
        </div>
        <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", background: "#f8fafc", padding: "10px 18px", borderRadius: 12, marginBottom: 16 }}>
          <span style={{ color: "#64748b", fontWeight: 700, fontSize: 11, letterSpacing: 1, textTransform: "uppercase" }}>
            Study all 6 endings
          </span>
          <div style={{ display: "flex", gap: 3 }}>
            {[0, 1, 2, 3, 4, 5].map((i) => (
              <div key={i} style={{ width: 8, height: 8, borderRadius: "50%", background: viewed.has(i) ? "#10b981" : "#cbd5e1", transition: "all 0.3s" }} />
            ))}
          </div>
        </div>
        <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 10 }}>
          {ER_VERB_ENDINGS.map((e, i) => {
            const isAct = activeEnding === i;
            const isViewed = viewed.has(i);
            const examples = VERB_EXAMPLES[e.subject];
            return (
              <div key={e.subject} onClick={() => handleLearnClick(i, e)}
                style={{
                  cursor: "pointer", padding: "18px 20px", borderRadius: 14,
                  borderLeft: `4px solid ${isAct ? "#0ea5e9" : isViewed ? "#10b981" : "#e2e8f0"}`,
                  background: isAct ? "linear-gradient(135deg, #0c4a6e, #0f172a)" : "#fff",
                  color: isAct ? "#fff" : "#0f172a", transition: "all 0.3s",
                  boxShadow: isAct ? "0 8px 20px rgba(14,165,233,0.15)" : "0 1px 3px rgba(0,0,0,0.04)",
                }}
              >
                <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: isAct ? 10 : 0 }}>
                  <span style={{ fontSize: 15, fontWeight: 700 }}>{e.subject}</span>
                  <span style={{ fontSize: 26, fontWeight: 900, fontFamily: "'Outfit', sans-serif", color: isAct ? "#7dd3fc" : "#0ea5e9" }}>
                    {e.ending}
                  </span>
                </div>
                {isAct && (
                  <div style={{ borderTop: "1px solid rgba(255,255,255,0.15)", paddingTop: 10, animation: "fadeIn 0.2s" }}>
                    <div style={{ fontSize: 10, color: "#94a3b8", marginBottom: 6, letterSpacing: 1, textTransform: "uppercase", fontFamily: "'JetBrains Mono', monospace" }}>Examples:</div>
                    {examples.map((ex, j) => (
                      <div key={j} onClick={(ev) => { ev.stopPropagation(); VoiceEngine.speak(ex.full); }}
                        style={{ fontSize: 13, color: "#bae6fd", cursor: "pointer", padding: "3px 0", display: "flex", alignItems: "center", gap: 6 }}>
                        <span>🔊</span> <ClickableSentence text={ex.full} style={{ color: "#bae6fd" }} />
                      </div>
                    ))}
                    <div style={{ fontSize: 11, color: "#475569", marginTop: 6, fontFamily: "'DM Sans'" }}>= {e.exampleEn}</div>
                  </div>
                )}
              </div>
            );
          })}
        </div>
        {viewed.size === 6 && (
          <button onClick={startQuiz}
            style={{
              marginTop: 24, padding: "14px 36px", background: "linear-gradient(135deg, #0ea5e9, #6366f1)",
              color: "#fff", border: "none", borderRadius: 14, fontWeight: 800, fontSize: 15,
              cursor: "pointer", fontFamily: "'Outfit', sans-serif", display: "block", margin: "24px auto 0",
              boxShadow: "0 8px 20px rgba(14,165,233,0.25)", animation: "bounceIn 0.4s",
            }}
          >
            🧪 START QUIZ ({QUIZ.length} questions)
          </button>
        )}
      </>
    );
  }

  // QUIZ PHASE
  const currentQ = QUIZ[quizIdx];
  return (
    <div style={{ textAlign: "center" }}>
      <div style={{ display: "flex", justifyContent: "center", gap: 6, marginBottom: 24 }}>
        {QUIZ.map((_, i) => (
          <div key={i} style={{
            width: 32, height: 6, borderRadius: 3,
            background: i < quizIdx ? "#10b981" : i === quizIdx ? "#0ea5e9" : "#e2e8f0",
            transition: "all 0.3s",
          }} />
        ))}
      </div>

      <div style={{
        background: "#0f172a", borderRadius: 20, padding: "36px 28px", maxWidth: 500, margin: "0 auto 24px",
        color: "#fff", boxShadow: "0 12px 30px rgba(0,0,0,0.2)",
      }}>
        <div style={{ fontSize: 11, color: "#64748b", letterSpacing: 2, textTransform: "uppercase", marginBottom: 12, fontFamily: "'JetBrains Mono', monospace" }}>
          Question {quizIdx + 1} / {QUIZ.length}
        </div>
        <div style={{ fontSize: 24, fontWeight: 800, fontFamily: "'Outfit', sans-serif", marginBottom: 24 }}>
          {currentQ.q}
        </div>

        <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 10 }}>
          {currentQ.options.map((opt) => (
            <button key={opt} onClick={() => quizStatus === "idle" && handleQuizAnswer(opt)}
              style={{
                padding: "14px 8px", borderRadius: 12, border: "none", fontWeight: 800, fontSize: 16,
                cursor: quizStatus === "idle" ? "pointer" : "default",
                background: quizStatus === "correct" && opt === currentQ.answer ? "#059669"
                  : quizStatus === "wrong" && opt === currentQ.answer ? "#0ea5e9"
                  : "rgba(255,255,255,0.08)",
                color: "#fff", transition: "all 0.2s", fontFamily: "'Outfit', sans-serif",
              }}
            >
              {opt}
            </button>
          ))}
        </div>

        {quizStatus === "correct" && <div style={{ marginTop: 14, color: "#4ade80", fontWeight: 700, animation: "fadeIn 0.2s" }}>✅ Correct!</div>}
        {quizStatus === "wrong" && <div style={{ marginTop: 14, color: "#fca5a5", fontWeight: 700, animation: "fadeIn 0.2s" }}>❌ Try again! Look at the ending for "{currentQ.subject}"</div>}
      </div>

      <button onClick={() => { setPhase("learn"); setActiveEnding(null); }}
        style={{ background: "none", border: "none", color: "#64748b", cursor: "pointer", fontSize: 12, textDecoration: "underline" }}
      >
        ← Back to study
      </button>
    </div>
  );
};

// ── VISUAL VOCAB 2 ────────────────────────────────────────────

const VisualVocab2Slide = ({ onUnlock }) => {
  const [currentIdx, setCurrentIdx] = useState(0);
  const [input, setInput] = useState("");
  const [status, setStatus] = useState("idle");
  const [completed, setCompleted] = useState(new Set());
  const [showHint, setShowHint] = useState(false);

  const item = VISUAL_VOCAB_2[currentIdx];

  const handleSubmit = () => {
    const clean = input.toLowerCase().trim();
    const answer = item.verb.toLowerCase();
    if (clean === answer) {
      VoiceEngine.sfx("success");
      VoiceEngine.speak(item.verb);
      setStatus("correct");
      const nc = new Set(completed); nc.add(currentIdx); setCompleted(nc);
      setTimeout(() => {
        if (nc.size === VISUAL_VOCAB_2.length) {
          VoiceEngine.sfx("unlock");
          setTimeout(onUnlock, 800);
        } else {
          let next = (currentIdx + 1) % VISUAL_VOCAB_2.length;
          while (nc.has(next)) next = (next + 1) % VISUAL_VOCAB_2.length;
          setCurrentIdx(next);
          setInput("");
          setStatus("idle");
          setShowHint(false);
        }
      }, 1200);
    } else {
      VoiceEngine.sfx("error");
      setStatus("wrong");
      setTimeout(() => setStatus("idle"), 1200);
    }
  };

  return (
    <div style={{ textAlign: "center" }}>
      <div style={{ background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 14, padding: "12px 18px", marginBottom: 20, textAlign: "left" }}>
        <p style={{ margin: 0, fontSize: 12, color: "#0369a1", fontFamily: "'DM Sans', sans-serif", lineHeight: 1.6 }}>
          {"💡"} <strong>CHALLENGE:</strong> Look at the icon and the English meaning, then type the French -ER verb. Use the pronunciation hint if stuck!
        </p>
      </div>

      <div style={{ display: "flex", justifyContent: "center", gap: 8, marginBottom: 24 }}>
        {VISUAL_VOCAB_2.map((v, i) => (
          <div key={i} style={{
            width: 40, height: 40, borderRadius: 12, display: "flex", alignItems: "center", justifyContent: "center",
            fontSize: 18, background: completed.has(i) ? "#dcfce7" : i === currentIdx ? "#e0f2fe" : "#f8fafc",
            border: i === currentIdx ? "2px solid #0ea5e9" : "1px solid #f1f5f9",
            opacity: completed.has(i) ? 0.5 : 1, transition: "all 0.2s",
          }}>
            {completed.has(i) ? "✅" : v.icon}
          </div>
        ))}
      </div>

      <div style={{
        background: "#fff", borderRadius: 20, padding: "36px 28px", maxWidth: 420, margin: "0 auto 20px",
        border: "2px solid #f1f5f9", boxShadow: "0 8px 24px rgba(0,0,0,0.06)",
      }}>
        <div style={{ fontSize: 56, marginBottom: 12 }}>{item.icon}</div>
        <div style={{ fontSize: 20, fontWeight: 700, color: "#0f172a", fontFamily: "'Outfit', sans-serif", marginBottom: 4 }}>
          {item.translation}
        </div>

        {showHint ? (
          <div style={{ fontSize: 13, color: "#0ea5e9", fontFamily: "'JetBrains Mono', monospace", marginBottom: 20 }}>
            Sounds like: /{item.pronunciation}/
          </div>
        ) : (
          <button onClick={() => setShowHint(true)}
            style={{ background: "none", border: "none", cursor: "pointer", fontSize: 12, color: "#94a3b8", marginBottom: 20, textDecoration: "underline dotted" }}>
            Need a pronunciation hint?
          </button>
        )}

        <div style={{ display: "flex", gap: 8, justifyContent: "center" }}>
          <input type="text" value={input}
            onChange={(e) => { setInput(e.target.value); setStatus("idle"); }}
            onKeyDown={(e) => e.key === "Enter" && handleSubmit()}
            placeholder="Type the French verb..."
            style={{
              padding: "12px 18px", fontSize: 18, fontWeight: 700, fontFamily: "'Outfit', sans-serif",
              textAlign: "center", background: "#f8fafc", border: "none",
              borderBottom: `3px solid ${status === "correct" ? "#22c55e" : status === "wrong" ? "#ef4444" : "#e2e8f0"}`,
              borderRadius: "8px 8px 0 0", outline: "none", width: 200, transition: "all 0.2s",
            }}
          />
          <button onClick={handleSubmit}
            style={{
              padding: "12px 20px", background: "#0ea5e9", color: "#fff", border: "none",
              borderRadius: 10, fontWeight: 800, cursor: "pointer", fontSize: 14, fontFamily: "'Outfit', sans-serif",
            }}>GO</button>
        </div>

        {status === "correct" && (
          <div style={{ marginTop: 14, color: "#059669", fontWeight: 800, animation: "bounceIn 0.3s" }}>
            {"✅"} {item.verb} — {item.translation}!
          </div>
        )}
        {status === "wrong" && (
          <div style={{ marginTop: 14, color: "#ef4444", fontSize: 13, animation: "fadeIn 0.2s" }}>
            {"❌"} Not quite. {showHint ? `It sounds like /${item.pronunciation}/` : "Try using the hint!"}
          </div>
        )}
      </div>

      <p style={{ color: "#94a3b8", fontSize: 12, fontFamily: "'DM Sans', sans-serif" }}>
        {completed.size} / {VISUAL_VOCAB_2.length} verbs identified
      </p>
    </div>
  );
};

// ── CARD MATCH GAME — Match conjugated verbs to subjects ──────

const CardMatchGame = ({ onUnlock }) => {
  const CARDS_DATA = [
    { subject: "Je", verb: "parle", full: "Je parle", en: "I speak" },
    { subject: "Tu", verb: "chantes", full: "Tu chantes", en: "You sing" },
    { subject: "Nous", verb: "mangeons", full: "Nous mangeons", en: "We eat" },
    { subject: "Vous", verb: "habitez", full: "Vous habitez", en: "You live" },
    { subject: "Elle", verb: "écoute", full: "Elle écoute", en: "She listens" },
    { subject: "Ils", verb: "jouent", full: "Ils jouent", en: "They play" },
  ];

  const [selectedSubject, setSelectedSubject] = useState(null);
  const [selectedVerb, setSelectedVerb] = useState(null);
  const [matched, setMatched] = useState({});
  const [feedback, setFeedback] = useState(null);
  const [attempts, setAttempts] = useState(0);
  const shuffledVerbs = useRef([...CARDS_DATA].sort(() => Math.random() - 0.5)).current;

  useEffect(() => {
    if (Object.keys(matched).length === CARDS_DATA.length) {
      VoiceEngine.sfx("unlock");
      setTimeout(onUnlock, 1200);
    }
  }, [matched]);

  const tryMatch = (subjectIdx, verbCard) => {
    setAttempts((a) => a + 1);
    const subjectCard = CARDS_DATA[subjectIdx];
    if (subjectCard.verb === verbCard.verb) {
      VoiceEngine.sfx("success");
      VoiceEngine.speak(verbCard.full);
      setMatched((p) => ({ ...p, [subjectCard.subject]: true }));
      setSelectedSubject(null);
      setSelectedVerb(null);
      setFeedback({ type: "success", msg: `${"✅"} ${verbCard.full} = ${verbCard.en}` });
      setTimeout(() => setFeedback(null), 1500);
    } else {
      VoiceEngine.sfx("error");
      setSelectedSubject(null);
      setSelectedVerb(null);
      setFeedback({ type: "error", msg: `${"❌"} ${subjectCard.subject} + "${verbCard.verb}" — Check the ending!` });
      setTimeout(() => setFeedback(null), 2000);
    }
  };

  const handleSubjectClick = (idx) => {
    if (matched[CARDS_DATA[idx].subject]) return;
    VoiceEngine.sfx("click");
    if (selectedVerb !== null) { tryMatch(idx, shuffledVerbs[selectedVerb]); }
    else { setSelectedSubject(idx); setSelectedVerb(null); }
  };

  const handleVerbClick = (idx) => {
    if (matched[shuffledVerbs[idx].subject]) return;
    VoiceEngine.sfx("click");
    if (selectedSubject !== null) { tryMatch(selectedSubject, shuffledVerbs[idx]); }
    else { setSelectedVerb(idx); setSelectedSubject(null); }
  };

  return (
    <div>
      <div style={{ background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 14, padding: "12px 18px", marginBottom: 20, textAlign: "left" }}>
        <p style={{ margin: 0, fontSize: 12, color: "#0369a1", fontFamily: "'DM Sans', sans-serif", lineHeight: 1.6 }}>
          {"💡"} <strong>MEMORY MATCH:</strong> Connect each subject to its conjugated verb.
          Endings: Je{"→"}<strong>-e</strong>, Tu{"→"}<strong>-es</strong>, Il/Elle{"→"}<strong>-e</strong>, Nous{"→"}<strong>-ons</strong>, Vous{"→"}<strong>-ez</strong>, Ils{"→"}<strong>-ent</strong>
        </p>
      </div>

      <div style={{ display: "grid", gridTemplateColumns: "1fr auto 1fr", gap: 16, alignItems: "start" }}>
        <div style={{ display: "flex", flexDirection: "column", gap: 8 }}>
          <div style={{ fontSize: 10, fontWeight: 800, color: "#94a3b8", textTransform: "uppercase", letterSpacing: 2, textAlign: "center", marginBottom: 4 }}>Subjects</div>
          {CARDS_DATA.map((card, idx) => {
            const isMatched = !!matched[card.subject];
            const isSel = selectedSubject === idx;
            return (
              <button key={card.subject} onClick={() => handleSubjectClick(idx)}
                style={{
                  padding: "14px 18px", borderRadius: 12, border: isSel ? "2px solid #0ea5e9" : "1px solid #f1f5f9", fontWeight: 800, fontSize: 16,
                  cursor: isMatched ? "default" : "pointer", textAlign: "center",
                  background: isMatched ? "#dcfce7" : isSel ? "#0ea5e9" : "#f8fafc",
                  color: isMatched ? "#059669" : isSel ? "#fff" : "#0f172a",
                  transition: "all 0.2s", transform: isSel ? "scale(1.04)" : "scale(1)",
                  opacity: isMatched ? 0.5 : 1, fontFamily: "'Outfit', sans-serif",
                }}>
                {card.subject} {isMatched && "✓"}
              </button>
            );
          })}
        </div>
        <div style={{ display: "flex", flexDirection: "column", alignItems: "center", justifyContent: "center", height: "100%", padding: "40px 0" }}>
          <div style={{ width: 2, flex: 1, background: "#e2e8f0" }} />
          <div style={{ padding: "8px 12px", background: "#f8fafc", borderRadius: 8, fontSize: 18, margin: "8px 0" }}>{"🔗"}</div>
          <div style={{ width: 2, flex: 1, background: "#e2e8f0" }} />
        </div>
        <div style={{ display: "flex", flexDirection: "column", gap: 8 }}>
          <div style={{ fontSize: 10, fontWeight: 800, color: "#94a3b8", textTransform: "uppercase", letterSpacing: 2, textAlign: "center", marginBottom: 4 }}>Conjugated Verbs</div>
          {shuffledVerbs.map((card, idx) => {
            const isMatched = !!matched[card.subject];
            const isSel = selectedVerb === idx;
            return (
              <button key={card.verb + idx} onClick={() => handleVerbClick(idx)}
                style={{
                  padding: "14px 18px", borderRadius: 12, border: isSel ? "2px solid #6366f1" : "1px solid #f1f5f9", fontWeight: 800, fontSize: 16,
                  cursor: isMatched ? "default" : "pointer", textAlign: "center",
                  background: isMatched ? "#dcfce7" : isSel ? "linear-gradient(135deg, #6366f1, #8b5cf6)" : "#fff",
                  color: isMatched ? "#059669" : isSel ? "#fff" : "#334155",
                  transition: "all 0.2s", transform: isSel ? "scale(1.04)" : "scale(1)",
                  opacity: isMatched ? 0.5 : 1, fontFamily: "'Outfit', sans-serif",
                }}>
                {card.verb} {isMatched && "✓"}
              </button>
            );
          })}
        </div>
      </div>

      {feedback && (
        <div style={{
          marginTop: 20, padding: "12px 20px", borderRadius: 12, textAlign: "center",
          background: feedback.type === "success" ? "#f0fdf4" : "#fef2f2",
          border: `1px solid ${feedback.type === "success" ? "#bbf7d0" : "#fecaca"}`,
          color: feedback.type === "success" ? "#166534" : "#991b1b",
          fontWeight: 700, fontSize: 13, fontFamily: "'DM Sans', sans-serif", animation: "fadeIn 0.2s",
        }}>
          {feedback.msg}
        </div>
      )}

      <div style={{ marginTop: 16, textAlign: "center", color: "#94a3b8", fontSize: 12, fontFamily: "'DM Sans'" }}>
        {Object.keys(matched).length} / {CARDS_DATA.length} matched {"•"} {attempts} attempts
      </div>
    </div>
  );
};

// ── NUANCE ────────────────────────────────────────────────────

const NuanceSlide = ({ onUnlock }) => {
  const [openCard, setOpenCard] = useState(null);
  const [read, setRead] = useState({ j: false, nous: false });

  const toggle = (id) => {
    VoiceEngine.sfx("click");
    setOpenCard(openCard === id ? null : id);
    const nr = { ...read, [id]: true }; setRead(nr);
    if (nr.j && nr.nous && (!read.j || !read.nous)) { VoiceEngine.sfx("unlock"); setTimeout(onUnlock, 1500); }
  };

  return (
    <div>
      <div onClick={() => toggle("j")}
        style={{
          cursor: "pointer", padding: "24px 28px", borderRadius: 20,
          border: `2px solid ${openCard === "j" ? "#f59e0b" : "#f1f5f9"}`,
          background: openCard === "j" ? "#fffbeb" : "#fff",
          transition: "all 0.3s", marginBottom: 14,
          boxShadow: openCard === "j" ? "0 6px 20px rgba(245,158,11,0.1)" : "none",
        }}
      >
        <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center" }}>
          <h3 style={{ margin: 0, fontSize: 15, fontWeight: 700, color: "#78350f", display: "flex", alignItems: "center", gap: 8, fontFamily: "'Outfit', sans-serif" }}>
            ⚠️ Anomaly: The "J'" Rule {read.j && "✅"}
          </h3>
          <span style={{ transform: openCard === "j" ? "rotate(180deg)" : "none", transition: "0.3s", fontSize: 16 }}>▼</span>
        </div>
        {openCard === "j" && (
          <div style={{ marginTop: 14, animation: "fadeIn 0.2s" }}>
            <p style={{ color: "#92400e", lineHeight: 1.6, fontSize: 14, fontFamily: "'DM Sans', sans-serif" }}>
              Vowel clash! When the verb starts with a vowel or H, <code style={{ background: "#fde68a", padding: "1px 5px", borderRadius: 4, fontSize: 13 }}>Je</code> transforms.
            </p>
            <div style={{ marginTop: 10, display: "flex", alignItems: "center", gap: 14, background: "rgba(255,255,255,0.5)", padding: 14, borderRadius: 10, fontSize: 16 }}>
              <span style={{ textDecoration: "line-through", opacity: 0.4, fontSize: 13 }}>Je écoute</span>
              <span style={{ color: "#f59e0b" }}>→</span>
              <button onClick={(e) => { e.stopPropagation(); VoiceEngine.speak("J'écoute"); }}
                style={{ background: "none", border: "none", cursor: "pointer", fontWeight: 700, fontSize: 16, color: "#b45309", fontFamily: "'Outfit', sans-serif" }}>
                <ClickableSentence text="J'écoute" /> 🔊
              </button>
            </div>
            <div style={{ marginTop: 8, fontSize: 12, color: "#92400e", opacity: 0.7, fontStyle: "italic", fontFamily: "'DM Sans', sans-serif" }}>
              = "I listen"
            </div>
          </div>
        )}
      </div>

      <div onClick={() => toggle("nous")}
        style={{
          cursor: "pointer", padding: "24px 28px", borderRadius: 20,
          border: `2px solid ${openCard === "nous" ? "#0ea5e9" : "#f1f5f9"}`,
          background: openCard === "nous" ? "#f0f9ff" : "#fff",
          transition: "all 0.3s",
          boxShadow: openCard === "nous" ? "0 6px 20px rgba(14,165,233,0.1)" : "none",
        }}
      >
        <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center" }}>
          <h3 style={{ margin: 0, fontSize: 15, fontWeight: 700, color: "#0c4a6e", display: "flex", alignItems: "center", gap: 8, fontFamily: "'Outfit', sans-serif" }}>
            ⚠️ Anomaly: -GER Verbs {read.nous && "✅"}
          </h3>
          <span style={{ transform: openCard === "nous" ? "rotate(180deg)" : "none", transition: "0.3s", fontSize: 16 }}>▼</span>
        </div>
        {openCard === "nous" && (
          <div style={{ marginTop: 14, animation: "fadeIn 0.2s" }}>
            <p style={{ color: "#0369a1", lineHeight: 1.6, fontSize: 14, fontFamily: "'DM Sans', sans-serif" }}>
              Soft "G" protection required. Keep the "E" to preserve pronunciation.
            </p>
            <div style={{ marginTop: 10, display: "flex", alignItems: "center", gap: 14, background: "rgba(255,255,255,0.5)", padding: 14, borderRadius: 10, fontSize: 16 }}>
              <span style={{ textDecoration: "line-through", opacity: 0.4, fontSize: 13 }}>Nous mangons</span>
              <span style={{ color: "#0ea5e9" }}>→</span>
              <button onClick={(e) => { e.stopPropagation(); VoiceEngine.speak("Nous mangeons"); }}
                style={{ background: "none", border: "none", cursor: "pointer", fontWeight: 700, fontSize: 16, color: "#0369a1", fontFamily: "'Outfit', sans-serif" }}>
                Nous mang<u>e</u>ons 🔊
              </button>
            </div>
            <div style={{ marginTop: 8, fontSize: 12, color: "#0369a1", opacity: 0.7, fontStyle: "italic", fontFamily: "'DM Sans', sans-serif" }}>
              = "We eat"
            </div>
          </div>
        )}
      </div>
    </div>
  );
};

// ── NEGATIVE ──────────────────────────────────────────────────

const NegativeSlide = ({ onUnlock }) => {
  const [isNeg, setIsNeg] = useState(false);
  const [done, setDone] = useState(false);

  const toggle = (val) => {
    VoiceEngine.sfx("click"); setIsNeg(val);
    if (val) VoiceEngine.speak("Je ne parle pas français"); else VoiceEngine.speak("Je parle français");
    if (val && !done) { VoiceEngine.sfx("unlock"); setDone(true); setTimeout(onUnlock, 1500); }
  };

  return (
    <div style={{ textAlign: "center" }}>
      <div style={{ display: "inline-flex", padding: 3, background: "#f1f5f9", borderRadius: 50, marginBottom: 36 }}>
        {[false, true].map((val) => (
          <button key={String(val)} onClick={() => toggle(val)}
            style={{
              padding: "10px 28px", borderRadius: 50, border: "none", fontWeight: 800, cursor: "pointer",
              transition: "all 0.3s", fontSize: 13, fontFamily: "'Outfit', sans-serif",
              background: isNeg === val ? (val ? "#dc2626" : "#fff") : "transparent",
              color: isNeg === val ? (val ? "#fff" : "#0ea5e9") : "#94a3b8",
              boxShadow: isNeg === val ? (val ? "0 2px 8px rgba(220,38,38,0.25)" : "0 2px 8px rgba(0,0,0,0.08)") : "none",
            }}
          >
            {val ? "NEGATIVE" : "POSITIVE"}
          </button>
        ))}
      </div>

      <div style={{
        padding: "36px 28px", borderRadius: 20,
        background: isNeg ? "#0f172a" : "#fff",
        border: isNeg ? "2px solid #dc2626" : "1px solid #f1f5f9",
        transition: "all 0.5s", maxWidth: 560, margin: "0 auto 28px",
        boxShadow: isNeg ? "0 0 30px rgba(220,38,38,0.1)" : "0 2px 8px rgba(0,0,0,0.04)",
      }}>
        {!isNeg ? (
          <p style={{ fontSize: "clamp(22px, 4.5vw, 32px)", margin: 0, fontWeight: 300, color: "#0f172a", fontFamily: "'Outfit', sans-serif" }}>
            <ClickableSentence text="Je" /> <strong style={{ color: "#0ea5e9" }}><ClickableSentence text="parle" /></strong> <ClickableSentence text="français." />
          </p>
        ) : (
          <p style={{ fontSize: "clamp(22px, 4.5vw, 32px)", margin: 0, fontWeight: 300, color: "#fff", fontFamily: "'Outfit', sans-serif" }}>
            <ClickableSentence text="Je" />{" "}
            <span style={{ background: "#dc2626", padding: "2px 8px", borderRadius: 6, fontWeight: 800, boxShadow: "0 0 12px rgba(220,38,38,0.4)" }}>
              <ClickableSentence text="ne" />
            </span>{" "}
            <ClickableSentence text="parle" />{" "}
            <span style={{ background: "#dc2626", padding: "2px 8px", borderRadius: 6, fontWeight: 800, boxShadow: "0 0 12px rgba(220,38,38,0.4)" }}>
              <ClickableSentence text="pas" />
            </span>{" "}
            <ClickableSentence text="français." />
          </p>
        )}
        <div style={{ marginTop: 14, opacity: 0.3, fontSize: 18 }}>🔊</div>
      </div>
      <p style={{ color: "#64748b", background: "#f8fafc", padding: 14, borderRadius: 12, border: "1px solid #f1f5f9", maxWidth: 420, margin: "0 auto", fontSize: 13, fontFamily: "'DM Sans', sans-serif" }}>
        Activate the <strong style={{ color: "#dc2626" }}>NE ... PAS</strong> protocol to invert the sentiment.
      </p>
    </div>
  );
};

// ── QUESTION ──────────────────────────────────────────────────

const QuestionSlide = ({ onUnlock }) => {
  const [mode, setMode] = useState("statement");
  const [solved, setSolved] = useState(false);

  const toggle = () => {
    const nm = mode === "statement" ? "question" : "statement";
    setMode(nm); VoiceEngine.sfx("click");
    if (nm === "question") VoiceEngine.speak("Est-ce que vous aimez le chocolat ?");
    else VoiceEngine.speak("Vous aimez le chocolat.");
    if (nm === "question" && !solved) { setSolved(true); VoiceEngine.sfx("unlock"); setTimeout(onUnlock, 1500); }
  };

  return (
    <div style={{ textAlign: "center" }}>
      <button onClick={toggle}
        style={{
          background: "#0f172a", color: "#7dd3fc", border: "1px solid rgba(14,165,233,0.25)",
          padding: "14px 28px", borderRadius: 12, fontFamily: "'JetBrains Mono', monospace",
          fontWeight: 700, fontSize: 13, cursor: "pointer", marginBottom: 28,
          boxShadow: "0 0 16px rgba(14,165,233,0.1)",
        }}
      >
        {mode === "statement" ? "> INITIATE QUESTION PROTOCOL" : "> REVERT TO STATEMENT"}
      </button>

      <div style={{
        background: "#0f172a", borderRadius: 20, padding: "40px 28px", maxWidth: 650, margin: "0 auto",
        borderTop: "1px solid #1e293b", boxShadow: "0 16px 40px rgba(0,0,0,0.25)",
      }}>
        <div style={{
          display: "flex", alignItems: "center", justifyContent: "center", flexWrap: "wrap", gap: 8,
          fontSize: "clamp(20px, 4.5vw, 36px)", fontWeight: 300, fontFamily: "'JetBrains Mono', monospace", color: "#fff",
        }}>
          {mode === "question" && (
            <span style={{
              fontWeight: 800, background: "#0ea5e9", color: "#0f172a", padding: "3px 12px", borderRadius: 6,
              boxShadow: "0 0 12px rgba(14,165,233,0.5)", animation: "fadeIn 0.2s",
            }}>
              <ClickableSentence text="Est-ce que" />
            </span>
          )}
          <ClickableSentence text="vous aimez le chocolat" style={{ color: "#e2e8f0" }} />
          <span style={{ color: "#0ea5e9", fontWeight: 800 }}>{mode === "statement" ? "." : "?"}</span>
        </div>
        <div style={{ marginTop: 20, opacity: 0.3 }}>🔊</div>
        <div style={{ marginTop: 12, fontSize: 13, color: "#64748b", fontStyle: "italic", fontFamily: "'DM Sans', sans-serif" }}>
          {mode === "question" ? '= "Do you like chocolate?"' : '= "You like chocolate."'}
        </div>
      </div>
    </div>
  );
};

// ── LISTENING ─────────────────────────────────────────────────

const ListeningExercise = ({ onUnlock }) => {
  const [isPlaying, setIsPlaying] = useState(false);
  const [selected, setSelected] = useState(null);
  const [status, setStatus] = useState("idle");
  const [showTranslation, setShowTranslation] = useState(false);

  const playAudio = () => {
    VoiceEngine.sfx("click"); setIsPlaying(true);
    VoiceEngine.speak("Nous écoutons la musique.", 0.78);
    setTimeout(() => setIsPlaying(false), 2500);
  };

  const handleCheck = () => {
    VoiceEngine.sfx("click");
    if (selected === "écoutons") {
      setStatus("correct"); VoiceEngine.sfx("success"); VoiceEngine.sfx("unlock"); setTimeout(onUnlock, 1500);
    } else { setStatus("wrong"); VoiceEngine.sfx("error"); setTimeout(() => setStatus("idle"), 1500); }
  };

  const optionTranslations = {
    "écoutez": "you listen (formal/plural)",
    "écoutons": "we listen",
    "écoutent": "they listen",
  };

  return (
    <div style={{ textAlign: "center" }}>
      <button onClick={playAudio} disabled={isPlaying}
        style={{
          width: 110, height: 110, borderRadius: "50%", border: "none",
          background: isPlaying ? "linear-gradient(135deg, #0ea5e9, #6366f1)" : "#0f172a",
          cursor: "pointer", display: "flex", alignItems: "center", justifyContent: "center",
          margin: "0 auto 28px", boxShadow: isPlaying ? "0 0 24px rgba(14,165,233,0.4)" : "0 6px 20px rgba(0,0,0,0.15)",
          transition: "all 0.3s", fontSize: 36,
        }}
      >
        {isPlaying ? "🌊" : "▶️"}
      </button>
      <p style={{ color: "#94a3b8", fontSize: 11, letterSpacing: 3, fontWeight: 700, textTransform: "uppercase", marginBottom: 8, fontFamily: "'JetBrains Mono', monospace" }}>
        Audio Signal Intercepted
      </p>
      <button onClick={() => setShowTranslation(!showTranslation)}
        style={{ background: "none", border: "none", cursor: "pointer", color: "#64748b", fontSize: 12, marginBottom: 20, fontFamily: "'DM Sans', sans-serif", textDecoration: "underline", textDecorationStyle: "dotted" }}
      >
        {showTranslation ? '🔽 "We listen to music."' : "💡 Show translation hint"}
      </button>
      <div style={{ display: "flex", justifyContent: "center", gap: 10, marginBottom: 28, flexWrap: "wrap" }}>
        {["écoutez", "écoutons", "écoutent"].map((opt) => (
          <button key={opt} onClick={() => { VoiceEngine.sfx("click"); setSelected(opt); VoiceEngine.speak(opt); }}
            style={{
              padding: "14px 28px", borderRadius: 12,
              border: selected === opt ? "2px solid #0ea5e9" : "1px solid #e2e8f0",
              background: selected === opt ? "#0ea5e9" : "#fff",
              color: selected === opt ? "#fff" : "#334155",
              fontWeight: 800, fontSize: 16, cursor: "pointer", transition: "all 0.2s",
              transform: selected === opt ? "scale(1.04)" : "scale(1)", fontFamily: "'Outfit', sans-serif",
              display: "flex", flexDirection: "column", alignItems: "center",
            }}
          >
            {opt}
            <span style={{ fontSize: 9, opacity: 0.5, fontWeight: 400, marginTop: 3, fontFamily: "'DM Sans', sans-serif" }}>
              {optionTranslations[opt]}
            </span>
          </button>
        ))}
      </div>
      {selected && (
        <button onClick={handleCheck}
          style={{
            padding: "14px 40px", background: "#0f172a", color: "#fff", border: "none",
            borderRadius: 50, fontWeight: 800, fontSize: 15, cursor: "pointer",
            boxShadow: "0 6px 20px rgba(0,0,0,0.15)", fontFamily: "'Outfit', sans-serif",
          }}
        >
          CONFIRM {status === "correct" ? "✅" : status === "wrong" ? "❌" : ""}
        </button>
      )}
    </div>
  );
};

// ── MATCHING ──────────────────────────────────────────────────

const MatchingExercise = ({ onUnlock }) => {
  const [matched, setMatched] = useState({});
  const [selectedFr, setSelectedFr] = useState(null);
  const shuffledEn = useRef([...MATCHING_PAIRS].sort(() => Math.random() - 0.5)).current;

  const handleFrClick = (id) => {
    if (matched[id]) return;
    VoiceEngine.sfx("click");
    VoiceEngine.speak(MATCHING_PAIRS.find((p) => p.id === id).french);
    setSelectedFr(id);
  };

  const handleEnClick = (pair) => {
    if (!selectedFr) return;
    VoiceEngine.sfx("click");
    if (selectedFr === pair.id) {
      VoiceEngine.sfx("success");
      const nm = { ...matched, [pair.id]: true }; setMatched(nm); setSelectedFr(null);
      if (Object.keys(nm).length === MATCHING_PAIRS.length) { VoiceEngine.sfx("unlock"); setTimeout(onUnlock, 1200); }
    } else { VoiceEngine.sfx("error"); setSelectedFr(null); }
  };

  return (
    <>
      <p style={{ textAlign: "center", color: "#64748b", marginBottom: 20, fontFamily: "'DM Sans', sans-serif", fontSize: 14 }}>
        Select a French item, then tap its English match.
      </p>
      <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 20 }}>
        <div style={{ display: "flex", flexDirection: "column", gap: 8 }}>
          {MATCHING_PAIRS.map((p, i) => (
            <button key={p.id} onClick={() => handleFrClick(p.id)}
              style={{
                display: "flex", alignItems: "center", gap: 10, padding: "14px 16px", borderRadius: 12, border: "none",
                borderLeft: `4px solid ${matched[p.id] ? "#10b981" : selectedFr === p.id ? "#0ea5e9" : "#e2e8f0"}`,
                background: matched[p.id] ? "#f0fdf4" : selectedFr === p.id ? "#f0f9ff" : "#f8fafc",
                cursor: matched[p.id] ? "default" : "pointer", textAlign: "left", fontFamily: "'Outfit', sans-serif",
                fontSize: 14, fontWeight: 600, color: matched[p.id] ? "#059669" : "#0f172a",
                transition: "all 0.2s", opacity: matched[p.id] ? 0.55 : 1,
              }}
            >
              <span style={{
                width: 24, height: 24, borderRadius: 6, background: matched[p.id] ? "#dcfce7" : "#e0f2fe",
                display: "flex", alignItems: "center", justifyContent: "center", fontSize: 10, fontWeight: 800,
                color: matched[p.id] ? "#059669" : "#0ea5e9", flexShrink: 0,
              }}>
                {matched[p.id] ? "✓" : i + 1}
              </span>
              <ClickableSentence text={p.french} />
            </button>
          ))}
        </div>
        <div style={{ display: "flex", flexDirection: "column", gap: 8 }}>
          {shuffledEn.map((p) => (
            <button key={p.id} onClick={() => handleEnClick(p)}
              style={{
                padding: "14px 16px", borderRadius: 12,
                border: matched[p.id] ? "1px solid #6ee7b7" : "1px solid #f1f5f9",
                background: matched[p.id] ? "#f0fdf4" : "#fff",
                cursor: matched[p.id] ? "default" : "pointer", textAlign: "left", fontFamily: "'DM Sans', sans-serif",
                fontSize: 14, color: matched[p.id] ? "#059669" : "#64748b",
                transition: "all 0.2s", opacity: matched[p.id] ? 0.55 : 1,
              }}
            >
              {p.english}
            </button>
          ))}
        </div>
      </div>
    </>
  );
};

// ── UNSCRAMBLE ────────────────────────────────────────────────

const UnscrambleExercise = ({ onUnlock }) => {
  const [idx, setIdx] = useState(0);
  const [order, setOrder] = useState([]);
  const [done, setDone] = useState(false);
  const item = UNSCRAMBLE_ITEMS[idx];

  useEffect(() => { setOrder([]); }, [idx]);

  const handleWord = (word) => {
    VoiceEngine.sfx("click");
    if (order.includes(word)) return;
    const newO = [...order, word]; setOrder(newO);
    VoiceEngine.speak(word);
    if (newO.length === item.words.length) {
      if (newO.join(" ") === item.correct) {
        VoiceEngine.sfx("success"); VoiceEngine.speak(item.correct); setDone(true);
        setTimeout(() => {
          if (idx < UNSCRAMBLE_ITEMS.length - 1) { setIdx((c) => c + 1); setDone(false); }
          else { VoiceEngine.sfx("unlock"); setTimeout(onUnlock, 1000); }
        }, 1500);
      } else { VoiceEngine.sfx("error"); setTimeout(() => setOrder([]), 500); }
    }
  };

  return (
    <div style={{ textAlign: "center" }}>
      <div style={{
        minHeight: 90, background: "#f8fafc", borderRadius: 16, border: "2px dashed #cbd5e1",
        display: "flex", alignItems: "center", justifyContent: "center", gap: 10, padding: 20, marginBottom: 20, flexWrap: "wrap",
      }}>
        {order.length === 0 && (
          <span style={{ color: "#94a3b8", fontWeight: 700, fontSize: 11, letterSpacing: 2, textTransform: "uppercase" }}>Assemble the code blocks</span>
        )}
        {order.map((w, i) => (
          <span key={i} style={{
            padding: "8px 18px", background: "#fff", borderRadius: 10, fontWeight: 800, fontSize: 16,
            boxShadow: "0 3px 10px rgba(0,0,0,0.06)", border: "1px solid #e2e8f0", animation: "fadeIn 0.15s", fontFamily: "'Outfit', sans-serif",
          }}>{w}</span>
        ))}
      </div>
      {done ? (
        <div style={{ color: "#059669", fontWeight: 800, fontSize: 18, animation: "bounceIn 0.3s" }}>✅ Sequence Verified!</div>
      ) : (
        <div style={{ display: "flex", justifyContent: "center", gap: 10, flexWrap: "wrap" }}>
          {item.words.map((word) => (
            <button key={word} onClick={() => handleWord(word)} disabled={order.includes(word)}
              style={{
                padding: "12px 24px", borderRadius: 12, border: "none", fontWeight: 800, fontSize: 16, cursor: "pointer",
                background: order.includes(word) ? "transparent" : "#0f172a",
                color: order.includes(word) ? "transparent" : "#fff",
                boxShadow: order.includes(word) ? "none" : "0 3px 10px rgba(0,0,0,0.15)",
                transition: "all 0.2s", fontFamily: "'Outfit', sans-serif",
              }}
            >{word}</button>
          ))}
        </div>
      )}
      <p style={{ marginTop: 28, color: "#94a3b8", fontSize: 12, fontFamily: "'JetBrains Mono', monospace", borderTop: "1px solid #f1f5f9", paddingTop: 14 }}>
        Target: "{item.translation}"
      </p>
    </div>
  );
};

// ── SPOT ERROR ────────────────────────────────────────────────

const SpotErrorExercise = ({ onUnlock }) => {
  const [revealed, setRevealed] = useState({});

  useEffect(() => {
    if (Object.keys(revealed).length === ERROR_CORRECTION_ITEMS.length) { VoiceEngine.sfx("unlock"); setTimeout(onUnlock, 1500); }
  }, [revealed]);

  return (
    <div style={{ display: "flex", flexDirection: "column", gap: 14 }}>
      {ERROR_CORRECTION_ITEMS.map((item) => (
        <div key={item.id} style={{
          background: "#f8fafc", border: "1px solid #f1f5f9", padding: "20px 24px", borderRadius: 16,
          display: "flex", justifyContent: "space-between", alignItems: "center", gap: 16, flexWrap: "wrap",
        }}>
          <div style={{ display: "flex", alignItems: "center", gap: 10 }}>
            <span style={{ background: "#fef3c7", padding: 8, borderRadius: "50%", fontSize: 18 }}>⚠️</span>
            <span style={{ fontSize: 16, fontWeight: 500, color: "#475569", textDecoration: "line-through", textDecorationColor: "#ef4444", textDecorationStyle: "wavy" }}>
              <ClickableSentence text={item.incorrect} />
            </span>
          </div>
          {revealed[item.id] ? (
            <div style={{ background: "#f0fdf4", padding: "12px 18px", borderRadius: 12, border: "1px solid #bbf7d0", flex: 1, minWidth: 180, animation: "fadeIn 0.2s" }}>
              <p style={{ margin: 0, fontWeight: 800, fontSize: 15, color: "#166534", display: "flex", alignItems: "center", gap: 6 }}>
                <ClickableSentence text={item.correct} />
                <button onClick={() => VoiceEngine.speak(item.correct)} style={{ background: "none", border: "none", cursor: "pointer", fontSize: 14, padding: 2 }}>🔊</button>
              </p>
              <p style={{ margin: "2px 0 0", fontSize: 11, color: "#059669", fontStyle: "italic", fontFamily: "'DM Sans', sans-serif" }}>= {item.correctEn}</p>
              <p style={{ margin: "4px 0 0", fontSize: 12, color: "#4ade80", fontFamily: "'DM Sans', sans-serif" }}>{item.explanation}</p>
            </div>
          ) : (
            <button onClick={() => { VoiceEngine.sfx("click"); VoiceEngine.speak(item.correct); setRevealed((p) => ({ ...p, [item.id]: true })); }}
              style={{
                padding: "8px 18px", borderRadius: 8, border: "none", background: "#e2e8f0", color: "#475569",
                fontWeight: 700, fontSize: 10, cursor: "pointer", letterSpacing: 1, textTransform: "uppercase", fontFamily: "'Outfit', sans-serif",
              }}
            >
              Debug Line
            </button>
          )}
        </div>
      ))}
    </div>
  );
};

// ── CONJUGATION ───────────────────────────────────────────────

const ConjugationExercise = ({ onUnlock }) => {
  // 20 questions covering all subjects and verbs learned
  const ALL_QUESTIONS = [
    { subject: "Je", verb: "parler", sentence: "_____ français.", answer: "parle", en: "I speak French." },
    { subject: "Tu", verb: "écouter", sentence: "_____ la musique.", answer: "écoutes", en: "You listen to music." },
    { subject: "Il", verb: "manger", sentence: "_____ une pizza.", answer: "mange", en: "He eats a pizza." },
    { subject: "Nous", verb: "habiter", sentence: "_____ à Paris.", answer: "habitons", en: "We live in Paris." },
    { subject: "Vous", verb: "chanter", sentence: "_____ bien.", answer: "chantez", en: "You sing well." },
    { subject: "Elles", verb: "danser", sentence: "_____ ensemble.", answer: "dansent", en: "They dance together." },
    { subject: "Je", verb: "regarder", sentence: "_____ la télé.", answer: "regarde", en: "I watch TV." },
    { subject: "Tu", verb: "jouer", sentence: "_____ au tennis.", answer: "joues", en: "You play tennis." },
    { subject: "Elle", verb: "travailler", sentence: "_____ beaucoup.", answer: "travaille", en: "She works a lot." },
    { subject: "Nous", verb: "voyager", sentence: "_____ en France.", answer: "voyageons", en: "We travel to France." },
    { subject: "Vous", verb: "étudier", sentence: "_____ le français.", answer: "étudiez", en: "You study French." },
    { subject: "Ils", verb: "cuisiner", sentence: "_____ le dîner.", answer: "cuisinent", en: "They cook dinner." },
    { subject: "Tu", verb: "aimer", sentence: "_____ le chocolat.", answer: "aimes", en: "You like chocolate." },
    { subject: "Je", verb: "nager", sentence: "_____ à la piscine.", answer: "nage", en: "I swim at the pool." },
    { subject: "On", verb: "dîner", sentence: "_____ à 20h.", answer: "dîne", en: "We dine at 8pm." },
    { subject: "Nous", verb: "chanter", sentence: "_____ une chanson.", answer: "chantons", en: "We sing a song." },
    { subject: "Vous", verb: "danser", sentence: "_____ le tango.", answer: "dansez", en: "You dance the tango." },
    { subject: "Ils", verb: "parler", sentence: "_____ anglais.", answer: "parlent", en: "They speak English." },
    { subject: "Tu", verb: "dessiner", sentence: "_____ un chat.", answer: "dessines", en: "You draw a cat." },
    { subject: "Je", verb: "téléphoner", sentence: "_____ à Marie.", answer: "téléphone", en: "I call Marie." },
  ];

  const [gameState, setGameState] = useState("ready"); // ready | playing | gameover | victory
  const [questions, setQuestions] = useState([]);
  const [currentIdx, setCurrentIdx] = useState(0);
  const [input, setInput] = useState("");
  const [lives, setLives] = useState(3);
  const [combo, setCombo] = useState(0);
  const [bestCombo, setBestCombo] = useState(0);
  const [score, setScore] = useState(0);
  const [showResult, setShowResult] = useState(null); // null | "correct" | "wrong"
  const [wrongAnswer, setWrongAnswer] = useState("");
  const [shakeScreen, setShakeScreen] = useState(false);
  const [timer, setTimer] = useState(0);
  const timerRef = useRef(null);
  const inputRef = useRef(null);

  const startGame = () => {
    const shuffled = [...ALL_QUESTIONS].sort(() => Math.random() - 0.5);
    setQuestions(shuffled);
    setCurrentIdx(0);
    setInput("");
    setLives(3);
    setCombo(0);
    setBestCombo(0);
    setScore(0);
    setShowResult(null);
    setWrongAnswer("");
    setTimer(0);
    setGameState("playing");
    VoiceEngine.sfx("unlock");
    timerRef.current = setInterval(() => setTimer((t) => t + 1), 1000);
    setTimeout(() => inputRef.current?.focus(), 300);
  };

  useEffect(() => {
    return () => { if (timerRef.current) clearInterval(timerRef.current); };
  }, []);

  const formatTime = (s) => {
    const m = Math.floor(s / 60);
    const sec = s % 60;
    return `${m}:${sec.toString().padStart(2, "0")}`;
  };

  const handleSubmit = () => {
    if (!input.trim() || showResult) return;
    const q = questions[currentIdx];
    const userAnswer = input.toLowerCase().trim();

    if (userAnswer === q.answer) {
      // CORRECT
      const newCombo = combo + 1;
      const points = 100 + (newCombo > 1 ? newCombo * 25 : 0);
      setCombo(newCombo);
      if (newCombo > bestCombo) setBestCombo(newCombo);
      setScore((s) => s + points);
      setShowResult("correct");

      // Sound: combo sounds get more exciting
      if (newCombo >= 5) {
        VoiceEngine.sfx("levelup");
      } else if (newCombo >= 3) {
        VoiceEngine.sfx("unlock");
      } else {
        VoiceEngine.sfx("success");
      }
      VoiceEngine.speak(q.subject + " " + q.answer);

      setTimeout(() => {
        if (currentIdx + 1 >= questions.length) {
          // VICTORY!
          clearInterval(timerRef.current);
          setGameState("victory");
          VoiceEngine.sfx("levelup");
          setTimeout(() => VoiceEngine.sfx("levelup"), 500);
          setTimeout(onUnlock, 2000);
        } else {
          setCurrentIdx((i) => i + 1);
          setInput("");
          setShowResult(null);
          setTimeout(() => inputRef.current?.focus(), 100);
        }
      }, 800);
    } else {
      // WRONG
      const newLives = lives - 1;
      setLives(newLives);
      setCombo(0);
      setShowResult("wrong");
      setWrongAnswer(q.answer);
      setShakeScreen(true);
      VoiceEngine.sfx("error");

      setTimeout(() => setShakeScreen(false), 400);

      if (newLives <= 0) {
        // GAME OVER
        setTimeout(() => {
          clearInterval(timerRef.current);
          setGameState("gameover");
        }, 1500);
      } else {
        setTimeout(() => {
          setShowResult(null);
          setInput("");
          setWrongAnswer("");
          setTimeout(() => inputRef.current?.focus(), 100);
        }, 2000);
      }
    }
  };

  // READY SCREEN
  if (gameState === "ready") {
    return (
      <div style={{ textAlign: "center" }}>
        <div style={{ fontSize: 64, marginBottom: 16 }}>🏆</div>
        <h3 style={{ fontSize: 28, fontWeight: 900, color: "#0f172a", margin: "0 0 12px", fontFamily: "'Outfit', sans-serif" }}>
          FINAL BOSS
        </h3>
        <p style={{ color: "#64748b", fontSize: 15, maxWidth: 480, margin: "0 auto 16px", lineHeight: 1.7, fontFamily: "'DM Sans', sans-serif" }}>
          20 conjugation challenges. 3 lives. Zero mercy.<br />
          Type the correct conjugated form for each verb to escape.
        </p>
        <div style={{
          background: "#0f172a", borderRadius: 16, padding: "20px 24px", maxWidth: 400, margin: "0 auto 24px",
          display: "grid", gridTemplateColumns: "1fr 1fr 1fr", gap: 16,
        }}>
          <div style={{ textAlign: "center" }}>
            <div style={{ fontSize: 24 }}>❤️❤️❤️</div>
            <div style={{ fontSize: 10, color: "#94a3b8", marginTop: 4, fontFamily: "'JetBrains Mono', monospace" }}>3 LIVES</div>
          </div>
          <div style={{ textAlign: "center" }}>
            <div style={{ fontSize: 24, fontWeight: 900, color: "#fff", fontFamily: "'Outfit'" }}>20</div>
            <div style={{ fontSize: 10, color: "#94a3b8", marginTop: 4, fontFamily: "'JetBrains Mono', monospace" }}>QUESTIONS</div>
          </div>
          <div style={{ textAlign: "center" }}>
            <div style={{ fontSize: 24 }}>🔥</div>
            <div style={{ fontSize: 10, color: "#94a3b8", marginTop: 4, fontFamily: "'JetBrains Mono', monospace" }}>COMBOS</div>
          </div>
        </div>
        <div style={{ background: "#f0f9ff", border: "1px solid #bae6fd", borderRadius: 14, padding: "12px 18px", marginBottom: 24, textAlign: "left", maxWidth: 480, margin: "0 auto 24px" }}>
          <p style={{ margin: 0, fontSize: 12, color: "#0369a1", fontFamily: "'DM Sans', sans-serif", lineHeight: 1.6 }}>
            💡 <strong>REMEMBER:</strong> Je→<strong>-e</strong> • Tu→<strong>-es</strong> • Il/Elle/On→<strong>-e</strong> • Nous→<strong>-ons</strong> • Vous→<strong>-ez</strong> • Ils/Elles→<strong>-ent</strong><br />
            ⚠️ Watch for: -GER verbs keep "e" with Nous (mangeons), and J' before vowels
          </p>
        </div>
        <button onClick={startGame}
          style={{
            padding: "18px 48px", background: "linear-gradient(135deg, #dc2626, #b91c1c)", color: "#fff",
            border: "none", borderRadius: 16, fontWeight: 900, fontSize: 18, cursor: "pointer",
            boxShadow: "0 8px 24px rgba(220,38,38,0.3)", fontFamily: "'Outfit', sans-serif",
            letterSpacing: 1, animation: "bounceIn 0.5s",
          }}
        >
          ⚔️ BEGIN FINAL EXAM
        </button>
      </div>
    );
  }

  // GAME OVER SCREEN
  if (gameState === "gameover") {
    return (
      <div style={{ textAlign: "center" }}>
        <div style={{ fontSize: 64, marginBottom: 16 }}>💀</div>
        <h3 style={{ fontSize: 28, fontWeight: 900, color: "#dc2626", margin: "0 0 12px", fontFamily: "'Outfit', sans-serif" }}>
          MISSION FAILED
        </h3>
        <p style={{ color: "#64748b", fontSize: 15, margin: "0 0 8px", fontFamily: "'DM Sans', sans-serif" }}>
          You reached question {currentIdx + 1} / {questions.length}
        </p>
        <p style={{ color: "#94a3b8", fontSize: 13, margin: "0 0 24px", fontFamily: "'DM Sans'" }}>
          Score: {score} pts • Best combo: {bestCombo}x • Time: {formatTime(timer)}
        </p>
        {wrongAnswer && (
          <div style={{ background: "#fef2f2", border: "1px solid #fecaca", borderRadius: 12, padding: "12px 20px", maxWidth: 400, margin: "0 auto 24px" }}>
            <p style={{ margin: 0, color: "#991b1b", fontSize: 13, fontFamily: "'DM Sans'" }}>
              The correct answer was: <strong>{questions[currentIdx]?.subject} {wrongAnswer}</strong><br />
              <span style={{ color: "#64748b", fontSize: 12 }}>{questions[currentIdx]?.en}</span>
            </p>
          </div>
        )}
        <button onClick={startGame}
          style={{
            padding: "16px 40px", background: "#0f172a", color: "#fff", border: "none",
            borderRadius: 14, fontWeight: 800, fontSize: 16, cursor: "pointer",
            fontFamily: "'Outfit', sans-serif", boxShadow: "0 6px 20px rgba(0,0,0,0.2)",
          }}
        >
          🔄 TRY AGAIN
        </button>
      </div>
    );
  }

  // VICTORY SCREEN
  if (gameState === "victory") {
    return (
      <div style={{ textAlign: "center", animation: "fadeIn 0.5s" }}>
        <div style={{ fontSize: 72, marginBottom: 16, animation: "bounceIn 0.6s" }}>🏆</div>
        <h3 style={{ fontSize: 32, fontWeight: 900, color: "#059669", margin: "0 0 12px", fontFamily: "'Outfit', sans-serif" }}>
          ESCAPED!
        </h3>
        <p style={{ color: "#64748b", fontSize: 16, margin: "0 0 24px", fontFamily: "'DM Sans', sans-serif" }}>
          You conquered all 20 conjugations!
        </p>
        <div style={{
          background: "#0f172a", borderRadius: 16, padding: "24px 28px", maxWidth: 420, margin: "0 auto 24px",
          display: "grid", gridTemplateColumns: "1fr 1fr 1fr", gap: 16,
        }}>
          <div style={{ textAlign: "center" }}>
            <div style={{ fontSize: 28, fontWeight: 900, color: "#4ade80", fontFamily: "'Outfit'" }}>{score}</div>
            <div style={{ fontSize: 9, color: "#94a3b8", marginTop: 2, fontFamily: "'JetBrains Mono', monospace", letterSpacing: 1 }}>POINTS</div>
          </div>
          <div style={{ textAlign: "center" }}>
            <div style={{ fontSize: 28, fontWeight: 900, color: "#f59e0b", fontFamily: "'Outfit'" }}>{bestCombo}x</div>
            <div style={{ fontSize: 9, color: "#94a3b8", marginTop: 2, fontFamily: "'JetBrains Mono', monospace", letterSpacing: 1 }}>BEST COMBO</div>
          </div>
          <div style={{ textAlign: "center" }}>
            <div style={{ fontSize: 28, fontWeight: 900, color: "#38bdf8", fontFamily: "'Outfit'" }}>{formatTime(timer)}</div>
            <div style={{ fontSize: 9, color: "#94a3b8", marginTop: 2, fontFamily: "'JetBrains Mono', monospace", letterSpacing: 1 }}>TIME</div>
          </div>
        </div>
        <div style={{ display: "flex", justifyContent: "center", gap: 8, marginBottom: 8 }}>
          {Array.from({ length: lives }).map((_, i) => <span key={i} style={{ fontSize: 20 }}>❤️</span>)}
          {Array.from({ length: 3 - lives }).map((_, i) => <span key={i} style={{ fontSize: 20, opacity: 0.2 }}>🖤</span>)}
        </div>
        <p style={{ color: "#94a3b8", fontSize: 12, fontFamily: "'DM Sans'" }}>{lives}/3 lives remaining</p>
      </div>
    );
  }

  // PLAYING SCREEN
  const q = questions[currentIdx];
  const progress = ((currentIdx) / questions.length) * 100;

  return (
    <div style={{ animation: shakeScreen ? "shake 0.3s ease-in-out" : "none" }}>
      <style>{`@keyframes shake { 0%,100% { transform:translateX(0); } 20% { transform:translateX(-8px); } 40% { transform:translateX(8px); } 60% { transform:translateX(-4px); } 80% { transform:translateX(4px); } }`}</style>

      {/* HUD BAR */}
      <div style={{
        display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 20,
        background: "#0f172a", borderRadius: 14, padding: "12px 18px",
      }}>
        {/* Lives */}
        <div style={{ display: "flex", gap: 4 }}>
          {Array.from({ length: 3 }).map((_, i) => (
            <span key={i} style={{ fontSize: 18, transition: "all 0.3s", opacity: i < lives ? 1 : 0.15 }}>
              {i < lives ? "❤️" : "🖤"}
            </span>
          ))}
        </div>
        {/* Score */}
        <div style={{ textAlign: "center" }}>
          <span style={{ fontSize: 18, fontWeight: 900, color: "#fff", fontFamily: "'Outfit'" }}>{score}</span>
          <span style={{ fontSize: 10, color: "#64748b", marginLeft: 4, fontFamily: "'JetBrains Mono', monospace" }}>PTS</span>
        </div>
        {/* Combo */}
        <div style={{ textAlign: "center" }}>
          {combo > 1 && (
            <span style={{
              fontSize: 14, fontWeight: 900, color: combo >= 5 ? "#f59e0b" : "#38bdf8",
              fontFamily: "'Outfit'", animation: "bounceIn 0.2s",
            }}>
              🔥 {combo}x COMBO
            </span>
          )}
        </div>
        {/* Timer */}
        <div style={{ fontSize: 14, fontWeight: 700, color: "#64748b", fontFamily: "'JetBrains Mono', monospace" }}>
          ⏱ {formatTime(timer)}
        </div>
      </div>

      {/* Progress bar */}
      <div style={{ width: "100%", height: 6, background: "#1e293b", borderRadius: 3, marginBottom: 24, overflow: "hidden" }}>
        <div style={{
          width: `${progress}%`, height: "100%", borderRadius: 3,
          background: lives === 3 ? "linear-gradient(90deg, #10b981, #34d399)" : lives === 2 ? "linear-gradient(90deg, #f59e0b, #fbbf24)" : "linear-gradient(90deg, #ef4444, #f87171)",
          transition: "width 0.5s ease", boxShadow: `0 0 8px ${lives === 3 ? "#10b981" : lives === 2 ? "#f59e0b" : "#ef4444"}`,
        }} />
      </div>

      {/* Question counter */}
      <div style={{ textAlign: "center", marginBottom: 8 }}>
        <span style={{
          fontSize: 11, fontWeight: 800, color: "#64748b", letterSpacing: 2,
          fontFamily: "'JetBrains Mono', monospace", textTransform: "uppercase",
        }}>
          Question {currentIdx + 1} / {questions.length}
        </span>
      </div>

      {/* Main question card */}
      <div style={{
        background: "linear-gradient(135deg, #0c4a6e, #0f172a)", borderRadius: 20, padding: "32px 28px",
        maxWidth: 520, margin: "0 auto", color: "#fff",
        boxShadow: "0 16px 40px rgba(14,165,233,0.15)",
      }}>
        {/* Verb + Subject */}
        <div style={{ display: "flex", alignItems: "center", justifyContent: "center", gap: 10, marginBottom: 8 }}>
          <span style={{
            background: "rgba(14,165,233,0.2)", border: "1px solid rgba(14,165,233,0.3)",
            padding: "4px 12px", borderRadius: 8, fontSize: 14, fontWeight: 800,
            color: "#7dd3fc", fontFamily: "'Outfit', sans-serif",
          }}>
            {q.subject}
          </span>
          <span style={{ fontSize: 14, color: "#64748b" }}>+</span>
          <span style={{
            background: "rgba(99,102,241,0.15)", border: "1px solid rgba(99,102,241,0.25)",
            padding: "4px 12px", borderRadius: 8, fontSize: 14, fontWeight: 800,
            color: "#a5b4fc", fontFamily: "'Outfit', sans-serif",
          }}>
            {q.verb}
          </span>
          <button onClick={() => VoiceEngine.speak(q.verb)} style={{ background: "none", border: "none", cursor: "pointer", fontSize: 14 }}>🔊</button>
        </div>

        {/* English hint */}
        <div style={{ fontSize: 12, color: "#475569", textAlign: "center", marginBottom: 20, fontStyle: "italic", fontFamily: "'DM Sans'" }}>
          {q.en}
        </div>

        {/* Sentence with blank */}
        <div style={{
          fontSize: "clamp(18px, 4vw, 26px)", fontWeight: 600, textAlign: "center",
          fontFamily: "'Outfit', sans-serif", marginBottom: 24, lineHeight: 1.6, color: "#e2e8f0",
        }}>
          {q.subject}{" "}
          <span style={{
            display: "inline-block", minWidth: 120, borderBottom: "3px dashed rgba(14,165,233,0.4)",
            color: showResult === "correct" ? "#4ade80" : showResult === "wrong" ? "#fca5a5" : "#7dd3fc",
            fontWeight: 900, transition: "all 0.2s",
          }}>
            {showResult === "correct" ? q.answer : showResult === "wrong" ? input : "?????"}
          </span>{" "}
          {q.sentence.replace("_____", "").trim()}
        </div>

        {/* Input */}
        {!showResult && (
          <div style={{ display: "flex", gap: 8, justifyContent: "center" }}>
            <input
              ref={inputRef}
              type="text"
              value={input}
              onChange={(e) => setInput(e.target.value)}
              onKeyDown={(e) => e.key === "Enter" && handleSubmit()}
              placeholder="Type your answer..."
              autoFocus
              style={{
                padding: "14px 20px", fontSize: 20, fontWeight: 800, fontFamily: "'Outfit', sans-serif",
                textAlign: "center", background: "rgba(255,255,255,0.08)", border: "none",
                borderBottom: "3px solid #38bdf8", color: "#fff", borderRadius: "10px 10px 0 0",
                outline: "none", width: 220, transition: "all 0.2s",
              }}
            />
            <button onClick={handleSubmit}
              style={{
                padding: "14px 24px", background: "#0ea5e9", color: "#fff", border: "none",
                borderRadius: 12, fontWeight: 900, cursor: "pointer", fontSize: 16,
                fontFamily: "'Outfit', sans-serif", boxShadow: "0 4px 12px rgba(14,165,233,0.3)",
              }}
            >
              ✓
            </button>
          </div>
        )}

        {/* Feedback */}
        {showResult === "correct" && (
          <div style={{ textAlign: "center", animation: "bounceIn 0.3s" }}>
            <div style={{ fontSize: 18, fontWeight: 900, color: "#4ade80" }}>
              ✅ CORRECT!
              {combo >= 5 && " 🔥🔥🔥 INCREDIBLE!"}
              {combo >= 3 && combo < 5 && " 🔥🔥 ON FIRE!"}
              {combo === 2 && " 🔥 DOUBLE!"}
            </div>
            {combo > 1 && (
              <div style={{ fontSize: 12, color: "#f59e0b", marginTop: 4, fontFamily: "'JetBrains Mono', monospace" }}>
                +{100 + combo * 25} pts ({combo}x combo bonus!)
              </div>
            )}
          </div>
        )}
        {showResult === "wrong" && (
          <div style={{ textAlign: "center", animation: "fadeIn 0.2s" }}>
            <div style={{ fontSize: 18, fontWeight: 900, color: "#fca5a5", marginBottom: 6 }}>
              ❌ WRONG — Life lost!
            </div>
            <div style={{ fontSize: 14, color: "#94a3b8" }}>
              Correct answer: <strong style={{ color: "#7dd3fc" }}>{q.subject} {q.answer}</strong>
            </div>
            <div style={{ fontSize: 12, color: "#64748b", marginTop: 2, fontFamily: "'DM Sans'" }}>
              Remember: {q.subject} → ending is <strong>{q.answer.slice(-3)}</strong>
            </div>
          </div>
        )}
      </div>
    </div>
  );
};

// ── FINAL REVIEW ──────────────────────────────────────────────

const FinalReviewSlide = ({ onUnlock }) => (
  <div style={{ textAlign: "center" }}>
    <div style={{
      width: 110, height: 110, borderRadius: "50%",
      background: "linear-gradient(135deg, #fef3c7, #fde68a)",
      display: "flex", alignItems: "center", justifyContent: "center",
      margin: "0 auto 28px", fontSize: 50,
      boxShadow: "0 0 40px rgba(251,191,36,0.25)", animation: "bounceIn 0.5s",
    }}>🏆</div>
    <h2 style={{ fontSize: 36, fontWeight: 900, color: "#0f172a", margin: "0 0 10px", fontFamily: "'Outfit', sans-serif" }}>
      MISSION COMPLETE
    </h2>
    <p style={{ color: "#64748b", fontSize: 15, maxWidth: 480, margin: "0 auto 36px", lineHeight: 1.7, fontFamily: "'DM Sans', sans-serif" }}>
      Archive integrity restored. You have mastered the -ER Verb Protocol.
    </p>
    <button onClick={() => { VoiceEngine.sfx("levelup"); onUnlock(); }}
      style={{
        padding: "14px 36px", background: "#0f172a", color: "#fff", border: "none",
        borderRadius: 50, fontWeight: 800, fontSize: 16, cursor: "pointer",
        boxShadow: "0 6px 20px rgba(0,0,0,0.15)", fontFamily: "'Outfit', sans-serif",
      }}
    >
      ⭐ VIEW FINAL EVALUATION
    </button>
  </div>
);

// ── CERTIFICATE ───────────────────────────────────────────────

const CertificateSlide = () => (
  <div style={{ textAlign: "center" }}>
    <div style={{
      background: "#fffbf0", border: "3px solid #0f172a", padding: "44px 36px", maxWidth: 600,
      margin: "0 auto", position: "relative", boxShadow: "0 16px 40px rgba(0,0,0,0.12)",
    }}>
      {[{ top: 10, left: 10 }, { top: 10, right: 10 }, { bottom: 10, left: 10 }, { bottom: 10, right: 10 }].map((pos, i) => (
        <div key={i} style={{ position: "absolute", ...pos, width: 10, height: 10, borderRadius: "50%", background: "#0f172a" }} />
      ))}
      <div style={{ display: "inline-block", background: "#0f172a", color: "#fff", padding: "3px 14px", fontSize: 9, fontWeight: 800, letterSpacing: 3, textTransform: "uppercase", marginBottom: 20 }}>
        Official Document
      </div>
      <h1 style={{ fontSize: "clamp(24px, 4.5vw, 38px)", fontWeight: 900, color: "#0f172a", margin: "0 0 3px", textTransform: "uppercase", fontFamily: "'Outfit', sans-serif" }}>
        Certificate of Mastery
      </h1>
      <p style={{ fontSize: 10, fontWeight: 700, color: "#94a3b8", letterSpacing: 3, textTransform: "uppercase", paddingBottom: 20, borderBottom: "1px solid #e2e8f0", marginBottom: 28 }}>
        -ER Verbs • Présent • A1.1.1
      </p>
      <p style={{ fontSize: 15, color: "#64748b", fontStyle: "italic", marginBottom: 6 }}>Awarded to Agent</p>
      <div style={{ borderBottom: "3px solid #0f172a", maxWidth: 360, margin: "0 auto 28px" }}>
        <input type="text" placeholder="YOUR NAME HERE"
          style={{
            width: "100%", textAlign: "center", fontSize: "clamp(20px, 4.5vw, 36px)", fontWeight: 900,
            background: "transparent", border: "none", outline: "none", color: "#0ea5e9",
            textTransform: "uppercase", paddingBottom: 6, fontFamily: "'Outfit', sans-serif",
          }}
        />
      </div>
      <p style={{ fontSize: 14, color: "#64748b", maxWidth: 400, margin: "0 auto 36px", lineHeight: 1.7, fontFamily: "'DM Sans', sans-serif" }}>
        For exceptional skill in decoding the <span style={{ fontWeight: 800, color: "#0f172a", background: "#fde68a", padding: "1px 5px" }}>-ER Verb Protocol</span> at the Present Tense and successfully escaping the simulation.
      </p>
      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-end", padding: "0 20px" }}>
        <div style={{ textAlign: "center" }}>
          <p style={{ margin: 0, fontWeight: 800, fontSize: 9, textTransform: "uppercase", color: "#0f172a" }}>Clearance</p>
          <p style={{ margin: 0, fontSize: 22, fontWeight: 900, color: "#0f172a", fontFamily: "'JetBrains Mono', monospace" }}>A1.1.1</p>
        </div>
        <div style={{
          width: 64, height: 64, borderRadius: "50%", border: "3px double #991b1b",
          display: "flex", alignItems: "center", justifyContent: "center", transform: "rotate(12deg)", opacity: 0.7,
        }}>
          <span style={{ fontSize: 8, fontWeight: 800, color: "#991b1b", textTransform: "uppercase", textAlign: "center", transform: "rotate(-12deg)", border: "1.5px solid #991b1b", padding: "1px 3px", lineHeight: 1.2 }}>
            Top<br />Secret
          </span>
        </div>
        <div style={{ textAlign: "center" }}>
          <div style={{ fontSize: 16, color: "#0ea5e9", fontStyle: "italic", marginBottom: 3 }}>Christophe.V</div>
          <p style={{ margin: 0, fontWeight: 800, fontSize: 9, textTransform: "uppercase", color: "#0f172a", borderTop: "2px solid #0f172a", paddingTop: 3 }}>Commander</p>
        </div>
      </div>
    </div>
    <p style={{ marginTop: 20, color: "#64748b", fontSize: 12, fontFamily: "'DM Sans', sans-serif" }}>Screenshot this screen to save your record.</p>
  </div>
);

// ═══════════════════════════════════════════════════════════════
// MAIN APP
// ═══════════════════════════════════════════════════════════════

const SECTIONS = [
  { id: "intro", title: "Briefing", comp: LessonPlanSlide },
  { id: "vocab1", title: "Identification", comp: VisualVocabSlide },
  { id: "stem", title: "The Stem", comp: DefinitionSlide },
  { id: "endings", title: "The Codes", comp: EndingsSlide },
  { id: "vocab2", title: "Expansion", comp: VisualVocab2Slide },
  { id: "cardmatch", title: "Card Match", comp: CardMatchGame },
  { id: "nuance", title: "Anomalies", comp: NuanceSlide },
  { id: "negative", title: "Negation", comp: NegativeSlide },
  { id: "questions", title: "Interrogation", comp: QuestionSlide },
  { id: "audio", title: "Signal Analysis", comp: ListeningExercise },
  { id: "match", title: "Translation", comp: MatchingExercise },
  { id: "unscramble", title: "Reconstruction", comp: UnscrambleExercise },
  { id: "error", title: "Debugging", comp: SpotErrorExercise },
  { id: "conjugation", title: "Final Exam", comp: ConjugationExercise },
  { id: "summary", title: "Escape", comp: FinalReviewSlide },
  { id: "cert", title: "Victory", comp: CertificateSlide },
];

export default function App() {
  const [level, setLevel] = useState(0);

  // Load best voice on mount
  useEffect(() => { VoiceEngine.loadBestVoice(); }, []);

  const unlockLevel = useCallback((cur) => {
    if (cur === level) {
      const next = level + 1; setLevel(next);
      setTimeout(() => {
        const el = document.getElementById(`section-${next}`);
        if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
      }, 500);
    }
  }, [level]);

  return (
    <div style={{
      display: "flex", background: "#020617", minHeight: "100vh",
      fontFamily: "'DM Sans', sans-serif", color: "#1e293b", overflowX: "hidden",
    }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;700;800&family=Outfit:wght@300;400;600;700;800;900&display=swap');
        @keyframes fadeIn { from { opacity:0; transform:translateY(14px); } to { opacity:1; transform:translateY(0); } }
        @keyframes bounceIn { 0% { transform:scale(0.8); opacity:0; } 60% { transform:scale(1.08); } 100% { transform:scale(1); opacity:1; } }
        @keyframes pulse { 0%,100% { opacity:1; } 50% { opacity:0.35; } }
        @keyframes tooltipIn { from { opacity:0; transform:translateX(-50%) translateY(6px); } to { opacity:1; transform:translateX(-50%) translateY(0); } }
        * { box-sizing: border-box; }
        body { margin: 0; background: #020617; }
        input::placeholder { color: #cbd5e1; }
        ::-webkit-scrollbar { width: 3px; }
        ::-webkit-scrollbar-track { background: #0f172a; }
        ::-webkit-scrollbar-thumb { background: #334155; border-radius: 2px; }
      `}</style>

      {/* Grid BG */}
      <div style={{
        position: "fixed", inset: 0, zIndex: 0, pointerEvents: "none", opacity: 0.06,
        backgroundImage: "linear-gradient(rgba(255,255,255,0.12) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.12) 1px, transparent 1px)",
        backgroundSize: "40px 40px",
      }} />

      {/* Floating particles */}
      <div style={{ position: "fixed", inset: 0, pointerEvents: "none", zIndex: 0, overflow: "hidden" }}>
        {Array.from({ length: 20 }, (_, i) => (
          <div key={i} style={{
            position: "absolute",
            left: `${Math.random() * 100}%`, top: `${Math.random() * 100}%`,
            width: Math.random() * 2.5 + 1, height: Math.random() * 2.5 + 1,
            borderRadius: "50%", background: "rgba(14,165,233,0.2)",
            animation: `floatP ${Math.random() * 15 + 10}s ease-in-out ${Math.random() * 5}s infinite alternate`,
          }} />
        ))}
        <style>{`@keyframes floatP { from { transform:translateY(0) translateX(0); } to { transform:translateY(-30px) translateX(15px); } }`}</style>
      </div>

      {/* SIDEBAR HUD */}
      <aside style={{
        display: "flex", flexDirection: "column", width: 240, height: "100vh", position: "sticky", top: 0,
        borderRight: "1px solid #1e293b", background: "rgba(8,12,25,0.96)", backdropFilter: "blur(12px)",
        zIndex: 50, color: "#94a3b8", overflowY: "auto", flexShrink: 0,
      }}>
        <div style={{ padding: "24px 20px", borderBottom: "1px solid #1e293b", background: "rgba(2,6,23,0.9)" }}>
          <div style={{ display: "flex", alignItems: "center", gap: 8, marginBottom: 16 }}>
            <div style={{ width: 6, height: 6, borderRadius: "50%", background: "#ef4444", animation: "pulse 2s infinite" }} />
            <span style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 9, color: "#ef4444", fontWeight: 700, letterSpacing: 3, textTransform: "uppercase" }}>Live Feed</span>
          </div>
          <h1 style={{ fontWeight: 900, fontSize: 20, color: "#fff", margin: "0 0 2px", lineHeight: 1, fontFamily: "'Outfit', sans-serif" }}>ESCAPE FLAB</h1>
          <p style={{ fontSize: 9, color: "#475569", fontWeight: 700, letterSpacing: 2, margin: "2px 0 0", textTransform: "uppercase", fontFamily: "'JetBrains Mono', monospace" }}>
            -ER Verbs • Présent
          </p>
          <p style={{ fontSize: 8, color: "#334155", fontWeight: 700, letterSpacing: 2, margin: "2px 0 0", textTransform: "uppercase" }}>Level A1.1.1</p>

          <div style={{ marginTop: 20 }}>
            <div style={{ display: "flex", justifyContent: "space-between", fontSize: 9, fontFamily: "'JetBrains Mono', monospace", color: "#38bdf8", marginBottom: 5 }}>
              <span>PROGRESS</span>
              <span>{Math.round((Math.min(level, SECTIONS.length) / SECTIONS.length) * 100)}%</span>
            </div>
            <div style={{ width: "100%", height: 3, background: "#1e293b", borderRadius: 3, overflow: "hidden" }}>
              <div style={{
                width: `${(level / SECTIONS.length) * 100}%`, height: "100%",
                background: "linear-gradient(90deg, #0ea5e9, #6366f1)",
                transition: "width 1s ease", boxShadow: "0 0 8px #0ea5e9", borderRadius: 3,
              }} />
            </div>
          </div>
        </div>

        <nav style={{ flex: 1, padding: "10px 10px" }}>
          {SECTIONS.map((s, idx) => {
            const isUnlocked = idx + 1 <= level;
            const isCurrent = idx + 1 === level;
            return (
              <div key={s.id} style={{
                display: "flex", alignItems: "center", gap: 8, padding: "8px 12px", borderRadius: 8, marginBottom: 1,
                fontSize: 10, fontWeight: 700, textTransform: "uppercase", letterSpacing: 0.8,
                transition: "all 0.2s",
                border: isCurrent ? "1px solid rgba(14,165,233,0.25)" : "1px solid transparent",
                background: isCurrent ? "rgba(14,165,233,0.06)" : "transparent",
                color: isCurrent ? "#38bdf8" : isUnlocked ? "rgba(52,211,153,0.55)" : "#1e293b",
              }}>
                <span style={{ fontSize: 10 }}>{isUnlocked ? "✅" : "🔒"}</span>
                {s.title}
              </div>
            );
          })}
        </nav>

        <div style={{
          padding: "10px 14px", borderTop: "1px solid #1e293b", fontSize: 8, color: "#1e293b",
          textAlign: "center", fontFamily: "'JetBrains Mono', monospace", letterSpacing: 1,
        }}>
          SECURE CONNECTION
        </div>
      </aside>

      {/* MAIN */}
      <main style={{ flex: 1, width: "100%", position: "relative", zIndex: 10 }}>
        <CoverSlide onStart={() => unlockLevel(0)} />
        <div style={{ paddingBottom: 120 }}>
          {SECTIONS.map((section, idx) => {
            const sectionLevel = idx + 1;
            return (
              <SectionLayout key={section.id} id={`section-${sectionLevel}`} title={section.title}
                isLocked={level < sectionLevel} index={sectionLevel}
              >
                <section.comp onUnlock={() => unlockLevel(sectionLevel)} />
              </SectionLayout>
            );
          })}
        </div>
      </main>
    </div>
  );
}
