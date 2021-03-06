# Duck Duck Go question solver

Spoken answers api for duck duck go

Language support provided by language translation plugins

```python
from neon_solver_ddg_plugin import DDGSolver

d = DDGSolver()

query = "who is Isaac Newton"

# full answer
ans = d.spoken_answer(query)
print(ans)
# Sir Isaac Newton was an English mathematician, physicist, astronomer, alchemist, theologian, and author widely recognised as one of the greatest mathematicians and physicists of all time and among the most influential scientists. He was a key figure in the philosophical revolution known as the Enlightenment. His book PhilosophiĆ¦ Naturalis Principia Mathematica, first published in 1687, established classical mechanics. Newton also made seminal contributions to optics, and shares credit with German mathematician Gottfried Wilhelm Leibniz for developing infinitesimal calculus. In the Principia, Newton formulated the laws of motion and universal gravitation that formed the dominant scientific viewpoint until it was superseded by the theory of relativity.


# chunked answer, "tell me more"
for sentence in d.long_answer(query):
    print(sentence["title"])
    print(sentence["summary"])
    print(sentence.get("img"))
    
    # who is Isaac Newton
    # Sir Isaac Newton was an English mathematician, physicist, astronomer, alchemist, theologian, and author widely recognised as one of the greatest mathematicians and physicists of all time and among the most influential scientists.
    # https://duckduckgo.com/i/ea7be744.jpg
    
    # who is Isaac Newton
    # He was a key figure in the philosophical revolution known as the Enlightenment.
    # https://duckduckgo.com/i/ea7be744.jpg
    
    # who is Isaac Newton
    # His book PhilosophiĆ¦ Naturalis Principia Mathematica, first published in 1687, established classical mechanics.
    # https://duckduckgo.com/i/ea7be744.jpg
    
    # who is Isaac Newton
    # Newton also made seminal contributions to optics, and shares credit with German mathematician Gottfried Wilhelm Leibniz for developing infinitesimal calculus.
    # https://duckduckgo.com/i/ea7be744.jpg
    
    # who is Isaac Newton
    # In the Principia, Newton formulated the laws of motion and universal gravitation that formed the dominant scientific viewpoint until it was superseded by the theory of relativity.
    # https://duckduckgo.com/i/ea7be744.jpg
    

# bidirectional auto translate by passing lang context
sentence = d.spoken_answer("Quem Ć© Isaac Newton",
                           context={"lang": "pt"})
print(sentence)
# Sir Isaac Newton foi um matemĆ”tico inglĆŖs, fĆ­sico, astrĆ“nomo, alquimista, teĆ³logo e autor amplamente reconhecido como um dos maiores matemĆ”ticos e fĆ­sicos de todos os tempos e entre os cientistas mais influentes. Ele era uma figura chave na revoluĆ§Ć£o filosĆ³fica conhecida como o Iluminismo. Seu livro PhilosophiĆ¦ Naturalis Principia Mathematica, publicado pela primeira vez em 1687, estabeleceu a mecĆ¢nica clĆ”ssica. Newton tambĆ©m fez contribuiĆ§Ćµes seminais para a Ć³ptica, e compartilha crĆ©dito com o matemĆ”tico alemĆ£o Gottfried Wilhelm Leibniz para desenvolver cĆ”lculo infinitesimal. No Principia, Newton formulou as leis do movimento e da gravitaĆ§Ć£o universal que formaram o ponto de vista cientĆ­fico dominante atĆ© ser superado pela teoria da relatividade
```
