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
# Sir Isaac Newton was an English mathematician, physicist, astronomer, alchemist, theologian, and author widely recognised as one of the greatest mathematicians and physicists of all time and among the most influential scientists. He was a key figure in the philosophical revolution known as the Enlightenment. His book Philosophiæ Naturalis Principia Mathematica, first published in 1687, established classical mechanics. Newton also made seminal contributions to optics, and shares credit with German mathematician Gottfried Wilhelm Leibniz for developing infinitesimal calculus. In the Principia, Newton formulated the laws of motion and universal gravitation that formed the dominant scientific viewpoint until it was superseded by the theory of relativity.


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
    # His book Philosophiæ Naturalis Principia Mathematica, first published in 1687, established classical mechanics.
    # https://duckduckgo.com/i/ea7be744.jpg
    
    # who is Isaac Newton
    # Newton also made seminal contributions to optics, and shares credit with German mathematician Gottfried Wilhelm Leibniz for developing infinitesimal calculus.
    # https://duckduckgo.com/i/ea7be744.jpg
    
    # who is Isaac Newton
    # In the Principia, Newton formulated the laws of motion and universal gravitation that formed the dominant scientific viewpoint until it was superseded by the theory of relativity.
    # https://duckduckgo.com/i/ea7be744.jpg
    

# bidirectional auto translate by passing lang context
sentence = d.spoken_answer("Quem é Isaac Newton",
                           context={"lang": "pt"})
print(sentence)
# Sir Isaac Newton foi um matemático inglês, físico, astrônomo, alquimista, teólogo e autor amplamente reconhecido como um dos maiores matemáticos e físicos de todos os tempos e entre os cientistas mais influentes. Ele era uma figura chave na revolução filosófica conhecida como o Iluminismo. Seu livro Philosophiæ Naturalis Principia Mathematica, publicado pela primeira vez em 1687, estabeleceu a mecânica clássica. Newton também fez contribuições seminais para a óptica, e compartilha crédito com o matemático alemão Gottfried Wilhelm Leibniz para desenvolver cálculo infinitesimal. No Principia, Newton formulou as leis do movimento e da gravitação universal que formaram o ponto de vista científico dominante até ser superado pela teoria da relatividade
```
