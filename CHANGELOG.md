# Changelog

## 0.1.1

- The skill asks Claude to lead with your question: to use the statements that answer it in one plain explanation, list the sources it used below it with their links, and explain a difficult term where it uses it, in everyday words: with the meaning HelloGem returns for it, or otherwise the term's clear standard meaning, adding nothing about the ingredient and nothing from its name. It asks Claude to leave out a term whose meaning or scope the result leaves unclear unless you ask, to keep sources' own hedges without adding its own, and to keep who says what in that list, not the answer, unless you ask who says what or a difference between sources is the answer.
- COSMILE Europe's function labels come with CosIng's meaning of the function they name and stay credited to COSMILE Europe, so Claude can explain them in plain words.
- Each CosIng cosmetic function comes with CosIng's own general description of that function, linked to [CosIng's function reference](https://ec.europa.eu/growth/tools-databases/cosing/reference/functions), so Claude can say what the function means without stretching it into a skin or health benefit.
- When several separate ingredients share a name, each match includes its own explanation in the same result. The skill asks Claude to explain what they share once, as a plain answer about the name you asked rather than a report on the entries, to explain a difference by what it means for your question, and to ask which you mean only when you could tell them apart; never to say separate entries are one ingredient, or to extend an answer to matches that weren't shown.
- A CosIng definition appears only on the entry CosIng gives it to, including through that entry's US INCI names. It's left out when it points at a formula or structure CosIng draws rather than writes out; the CosIng link stays.
- Chemical roles, from ChEBI or inferred by HelloGem from cosmetic functions, stay in every result, and the skill asks Claude to leave them out unless you ask about chemistry.

## 0.1.0

- First release: the `explain-ingredient` skill and a connection to HelloGem's read-only service.
