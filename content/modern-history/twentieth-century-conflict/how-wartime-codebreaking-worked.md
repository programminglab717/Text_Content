# How Wartime Codebreaking Worked

Press a key on a German Enigma machine and several things happen before a letter appears. The rightmost rotor steps one position. Current leaves the key, passes through a plugboard where pairs of letters have been swapped by patch cords, runs through three rotating wheels whose internal wiring scrambles it three times over, hits a reflector at the end of the stack that sends it back, passes through the three wheels again by a different path, through the plugboard a second time, and lights a small bulb under a frosted letter. The operator reads the bulb and writes it down. Nobody in the room knows what route the current took, and the next letter will take a completely different one, because the wheel has moved again.

That is a good cipher. It was not, in the end, good enough, and the reasons why are a useful lesson in what actually protects a secret.

## What Made It Look Impossible

The security of Enigma rested on its settings, changed daily according to a printed key sheet: which three rotors were chosen from the available set and in what order, where each rotor's alphabet ring was clamped, where each wheel started, and which pairs of letters were cross-connected on the plugboard. Multiply those choices together and the number of possible configurations is enormous — far beyond anything that could be tried one at a time by hand, and large enough that German cryptographic authorities remained confident in the system to the end of the war.

But the size of a key space is not the same thing as security. What matters is whether there is a shortcut, and whether the people operating the machine give you one. Enigma had a structural shortcut built into it, and its users handed over the rest.

## The Letter That Could Not Be Itself

The shortcut was the reflector. Because current went into the rotor stack and came back out again, the wiring was necessarily reciprocal: if A enciphered to Q under some setting, then Q enciphered to A. That made the machine convenient — the same setting both enciphered and deciphered, so no operator had to remember a separate mode — and it had a fatal consequence. No letter could ever encipher as itself.

That single fact turns a guess into a test. Suppose you suspect a message contains the word WETTERBERICHT, weather report. Slide the guess along the ciphertext. Anywhere the guess puts a W above a W, or a T above a T, that position is impossible and can be discarded instantly. Usually only a handful of alignments survive. A surviving alignment is a crib: a stretch of plaintext matched to a stretch of ciphertext, and therefore a set of simultaneous constraints on what the machine must have been doing.

Turning those constraints into a daily key was the work of machinery. Polish mathematicians — Marian Rejewski above all, working with Jerzy Różycki and Henryk Zygalski — had broken into Enigma in the early 1930s using permutation theory and material obtained by French intelligence, and had built an electromechanical device they called the bomba. In the summer of 1939, with invasion obviously coming, they handed everything they had to British and French officers at a meeting outside Warsaw. That handover saved Britain years.

At Bletchley Park, Alan Turing designed a far more general machine around the crib idea. His bombe chained together replicas of Enigma's rotor stacks wired to reflect the relationships in a crib, and then spun through positions looking not for the answer but for contradictions. Almost every setting produced an inconsistency within microseconds and was rejected; the machine stopped only at settings that might be right. Gordon Welchman's addition of the diagonal board, which exploited the reciprocal nature of the plugboard as well, cut the number of false stops enormously and made the whole process practical. By the end of the war hundreds of bombes were running in outstations around southern England, most of them operated by Wrens on shifts, in rooms that smelled of hot oil and were loud enough to make conversation difficult.

## Cribs, Gardening, and Bad Habits

Everything depended on having a crib, which meant that the real attack surface was not the machine but the people using it. German signals discipline degraded steadily under operational pressure, and Bletchley made a study of the degradation.

Weather stations transmitted reports in a fixed format at fixed times. Quiet outposts sent messages that consisted of some variant of "nothing to report," day after day. Messages ended with predictable salutes to the head of state. Operators under time pressure chose message start positions that were easy to type — three adjacent keys, or the same letter three times, or the first three letters of a girlfriend's name, and the same one again the next day. Some units retransmitted an identical text on a different circuit whose key was already broken, which hands the analyst a plaintext and a ciphertext together.

The Royal Air Force took this further and manufactured cribs deliberately, a practice the codebreakers called gardening. Mine a particular stretch of coastal water and the Germans would transmit a warning message naming the location in a form that could be predicted almost word for word. Occasionally the intelligence value of the minelaying was in the reply rather than the mines.

There were also periods of outright blackout, and they were brutal. When the German navy introduced a four-rotor Enigma for Atlantic U-boats early in 1942, Bletchley lost the submarine traffic for the better part of a year, precisely as convoy losses peaked. It came back partly because of a boarding: when a U-boat was forced to the surface in the eastern Mediterranean that autumn, two British sailors swam to the sinking hull and passed up code material before it went down. Both drowned. A sixteen-year-old canteen assistant who had gone across with them got out.

## The Fish

Enigma carried operational traffic. The German high command's own messages went by a different route entirely: teleprinter links using Lorenz attachments that added a pseudorandom key stream to the characters with what we would now call an exclusive-or. British analysts called the system Tunny and the family of such links Fish, and they never saw one of the machines until the war was nearly over.

The break came from a single operator error in 1941. A long message sent from Athens to Vienna was not received properly, and was retransmitted on the same key setting with small changes in wording and abbreviation. That gave John Tiltman two versions of the same key stream, enough to strip out the key and recover both texts. From that key stream alone, Bill Tutte spent months deducing the internal structure of a machine he had never laid eyes on — how many wheels it had, how many positions each one held, and how they interacted.

Breaking it in daily practice required statistical testing at a speed no relay machine could manage. Tommy Flowers, a Post Office engineer, argued that thousands of thermionic valves could be made reliable if you simply never switched them off, which nobody senior believed. He built Colossus anyway, largely on his own initiative, and the first one ran at the end of 1943. It was electronic, programmable after a fashion through switches and plugs, and fast enough to matter. Several were running by the time of the Normandy landings, reading traffic between Berlin and its army groups.

## The Pacific Problem

Japanese systems required different tools. The main naval code, known to the Americans as JN-25, was not a machine cipher at all but a code book of five-digit groups, superenciphered by adding numbers drawn from a separate table of random additives. Breaking it was a grinding statistical exercise: recover the additive stream, strip it away, and then rebuild the meanings of code groups from context, over and over, as the books were replaced.

It was incomplete work, and the classic demonstration of using it well came before Midway in 1942. Decrypts referred repeatedly to an objective called "AF," which American analysts at Pearl Harbor believed to be Midway atoll but could not prove. They had Midway send a plain-language message about a failure of its water distillation plant. A Japanese report shortly afterward noted that AF was short of fresh water. The following year, a decrypted itinerary allowed American fighters to intercept and kill Admiral Yamamoto over the Solomons.

Separately, an American team under William Friedman had reconstructed the Japanese diplomatic cipher machine — stepping switches rather than rotors — without ever seeing it, and the resulting diplomatic traffic often told the Allies more about German intentions than about Japanese ones, because Japan's ambassador in Berlin was thorough and his reports were long.

Going the other way, the Americans also solved the problem by refusing to play. Marine units in the Pacific transmitted tactical orders in Navajo, using a vocabulary of substitutions agreed in advance by native speakers. It was fast, it needed no equipment, and it was never broken.

## Using It Without Losing It

The hardest discipline was not reading the traffic but acting on it. Every decision visibly informed by a decrypt risks telling the enemy his cipher is compromised, which costs you everything. So Ultra intelligence circulated to a tiny list, was never quoted in operational orders, and was acted on only when a plausible alternative explanation could be manufactured — a reconnaissance aircraft sent to be seen over a convoy before it was attacked, a routing change explained by a routine patrol.

The persistent legend that Coventry was left undefended to protect the secret does not survive examination; the evidence indicates the target was not identified in time for any such choice to be made. But the dilemma the legend dramatises was entirely real, and was faced in smaller versions constantly.

It is worth remembering that the traffic ran both ways. German naval intelligence read the British convoy cipher through much of the same period, and knew where convoys were going while Bletchley was dark. The Atlantic in 1942 was a battle in which each side was partly reading the other's mail. That is the part usually left out of the story, and it is the part with the most general lesson in it: the side that keeps its own signals secure is doing work every bit as valuable as the side that breaks the other's, and it gets no anecdotes for it.
