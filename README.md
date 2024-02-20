# Barh-Chart-using-data-from-web-site

import matplotlib.pyplot as plt
import pandas as pd

bank = pd.read_html("https://en.wikipedia.org/wiki/List_of_banks_in_India")

bank = bank[0][["Anchor Bank","Branches"]].sort_values("Anchor Bank", ascending=True)

plt.barh(bank["Anchor Bank"],bank["Branches"])
plt.xlabel("Count of Branches")
plt.ylabel("Bank names")
plt.title("Banks VS Count of Branches")
plt.show()
