
Spoken answers api for duck duck go


```python
d = DDG()
for sentence in d.spoken_answers("who is Isaac Newton"):
    # generator, yields extra info in each sentence
    # a good pattern is to speak the first sentence (short answer) 
    # and expose the other in a "tell me more" interaction
    print(sentence)
```

```
Sir Isaac Newton was an English mathematician, physicist, astronomer, theologian, and author widely recognised as one of the greatest mathematicians, physicists, and most influential scientists of all time.
He was a key figure in the philosophical revolution known as the Enlightenment.
His book Philosophiæ Naturalis Principia Mathematica, first published in 1687, established classical mechanics.
Newton also made seminal contributions to optics, and shares credit with German mathematician Gottfried Wilhelm Leibniz for developing infinitesimal calculus.
In Principia, Newton formulated the laws of motion and universal gravitation that formed the dominant scientific viewpoint until it was superseded by the theory of relativity.
Newton used his mathematical description of gravity to derive Kepler's laws of planetary motion, account for tides, the trajectories of comets, the precession of the equinoxes and other phenomena, eradicating doubt about the Solar System's heliocentricity.
```

Language support provided by language translation plugins

```python
d = DDG()
for sentence in d.spoken_answers("Quem é Isaac Newton", lang="pt"):
    print(sentence)
```

```
Sir Isaac Newton foi um matemático inglês, físico, astrônomo, teólogo e autor amplamente reconhecido como um dos maiores matemáticos, físicos e cientistas mais influentes de todos os tempos.
Ele era uma figura chave na revolução filosófica conhecida como Iluminismo.
Seu livro Philosophiæ Naturalis Principia Mathematica, publicado pela primeira vez em 1687, estabeleceu a mecânica clássica.
Newton também fez contribuições seminais para a óptica, e compartilha crédito com o matemático alemão Gottfried Wilhelm Leibniz para desenvolver cálculo infinitesimal.
Em Principia, Newton formulou as leis do movimento e da gravitação universal que formaram o ponto de vista científico dominante até que foi substituído pela teoria da relatividade.
Newton usou sua descrição matemática da gravidade para derivar as leis de Kepler do movimento planetário, conta para as marés, as trajetórias dos cometas, a precessão dos equinócios e outros fenômenos, erradicando dúvidas sobre a heliocentricidade do Sistema Solar
```
