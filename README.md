# KI-Modeberater-Generative-Outfit-Empfehlungen-mit-Stilanalyse
KI-Modeberater analysiert den persönlichen Stil des Nutzers und generiert maßgeschneiderte Outfit-Empfehlungen, die auf den vorhandenen Kleidungsstücken im Schrank basieren und aktuelle Modetrends berücksichtigen.
class Kleidungsstueck:
    def __init__(self, typ, farbe, stil):
        self.typ = typ
        self.farbe = farbe
        self.stil = stil

class Modeberater:
    def __init__(self):
        self.kleiderschrank = []

    def kleidung_hinzufuegen(self, kleidungsstueck):
        self.kleiderschrank.append(kleidungsstueck)

    def persoenlichen_stil_analysieren(self):
        # Hier könnte eine komplexere Analyse implementiert werden
        stile = [kleidung.stil for kleidung in self.kleiderschrank]
        beliebtester_stil = max(set(stile), key=stile.count)
        return beliebtester_stil

    def outfits_generieren(self):
        beliebtester_stil = self.persoenlichen_stil_analysieren()
        passende_kleidungsstuecke = [k for k in self.kleiderschrank if k.stil == beliebtester_stil]
        # Einfache Logik zur Generierung eines Outfits
        # Hier könnte eine komplexere Logik implementiert werden, die aktuelle Modetrends berücksichtigt
        outfit = passende_kleidungsstuecke[:3]  # Wählen Sie einfach die ersten 3 passenden Kleidungsstücke
        return outfit

# Beispiel
berater = Modeberater()
berater.kleidung_hinzufuegen(Kleidungsstueck('Hose', 'blau', 'casual'))
berater.kleidung_hinzufuegen(Kleidungsstueck('Shirt', 'weiß', 'casual'))
berater.kleidung_hinzufuegen(Kleidungsstueck('Schuhe', 'schwarz', 'casual'))

outfit = berater.outfits_generieren()
for kleidungsstueck in outfit:
    print(f"{kleidungsstueck.typ} in {kleidungsstueck.farbe} ({kleidungsstueck.stil})")
