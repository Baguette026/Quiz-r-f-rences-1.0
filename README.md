import random
import time

references = [
{"date":1576,"rep":"Jean Bodin — La République"},
{"date":1705,"rep":"Bernard de Mandeville — La fable des abeilles"},
{"date":1758,"rep":"François Quesnay — Tableau économique"},
{"date":1776,"rep":"Adam Smith — Richesse des nations"},
{"date":1798,"rep":"Thomas Malthus — Essai sur le principe de population"},
{"date":1803,"rep":"Jean-Baptiste Say — Traité d'économie politique"},
{"date":1817,"rep":"David Ricardo — Principes de l'économie politique et de l'impôt"},
{"date":1848,"rep":"Marx & Engels — Manifeste du parti communiste"},
{"date":1871,"rep":"Jevons — Théorie de l'économie politique"},
{"date":1871,"rep":"Carl Menger — Fondements d'économie politique"},
{"date":1874,"rep":"Léon Walras — Éléments d'économie politique pure"},
{"date":1890,"rep":"Alfred Marshall — Principes d'économie politique"},
{"date":1899,"rep":"Thorstein Veblen — Théorie de la classe de loisir"},
{"date":1911,"rep":"Schumpeter — Theory of Economic Development"},
{"date":1920,"rep":"Pigou — Economics of Welfare"},
{"date":1936,"rep":"Keynes — Théorie générale"},
{"date":1944,"rep":"Hayek — La route de la servitude"},
{"date":1944,"rep":"Polanyi — La grande transformation"},
{"date":1954,"rep":"Arrow & Debreu — Existence of an Equilibrium for a Competitive Economy"},
{"date":1956,"rep":"Solow — A Contribution to the Theory of Economic Growth"},
{"date":1960,"rep":"Rostow — Les étapes de la croissance économique"},
{"date":1960,"rep":"Coase — The Problem of Social Cost"},
{"date":1965,"rep":"Mancur Olson — Logic of Collective Action"},
{"date":1968,"rep":"Garrett Hardin — Tragedy of the Commons"},
{"date":1970,"rep":"Akerlof — Market for Lemons"},
{"date":1986,"rep":"Romer — Increasing Returns and Long-Run Growth"},
{"date":1988,"rep":"Lucas — Mechanics of Economic Development"},
{"date":1990,"rep":"Douglass North — Institutions, Institutional Change and Economic Performance"},
{"date":2012,"rep":"Acemoglu & Robinson — Why Nations Fail"},
{"date":2013,"rep":"Piketty — Le capital au XXIe siècle"},
{"date":2016,"rep":"Robert Gordon — Rise and Fall of American Growth"},
{"date":2016,"rep":"Branko Milanovic — Global Inequality"},
{"date":2020,"rep":"Aghion — Le pouvoir de la destruction créatrice"},
{"date":2020,"rep":"Banerjee & Duflo — Économie utile pour des temps difficiles"}
]

score = 0
start = time.time()

while time.time() - start < 180:

    q = random.choice(references)
    correct = q["rep"]

    options = [correct]

    while len(options) < 4:
        r = random.choice(references)["rep"]
        if r not in options:
            options.append(r)

    random.shuffle(options)

    print("\nDate :", q["date"])
    for i,opt in enumerate(options):
        print(i+1,"-",opt)

    rep = int(input("Choix : "))

    if options[rep-1] == correct:
        print("Correct")
        score += 1
    else:
        print("Faux — réponse :",correct)

print("\nTemps écoulé")
print("Score :",score)
