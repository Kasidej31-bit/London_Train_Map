import matplotlib.pylab as plt
import networkx as nx

plt.figure(figsize=(16, 9))
G = nx.Graph()

# Add Nodes for each line
lines = {
    "Piccadilly": [f"A{i}" for i in range(1, 7)],
    "Central": [f"B{i}" for i in range(1, 7)],
    "Northern": [f"C{i}" for i in range(1, 7)],
    "Jubilee": [f"D{i}" for i in range(1, 7)]
}

for line_name, nodes in lines.items():
    for node in nodes:
        G.add_node(node, line=line_name)

# Define Edges
piccadilly_edges = [("A1", "A2"), ("A2", "A3"), ("A3", "A4"), ("A4", "A5"), ("A5", "A6")]
central_edges = [("B1", "B2"), ("B2", "B3"), ("B3", "B4"), ("B4", "B5"), ("B5", "B6")]
northern_edges = [("C1", "C2"), ("C2", "C3"), ("C3", "C4"), ("C4", "C5"), ("C5", "C6")]
jubilee_edges = [("D1", "D2"), ("D2", "D3"), ("D3", "D4"), ("D4", "D5"), ("D5", "D6")]

G.add_edges_from(piccadilly_edges + central_edges + northern_edges + jubilee_edges)

# Position for each node
pos = {
    "A1": (1, 1),   "A2": (4, 5),   "A3": (8, 5),   "A4": (12, 5),  "A5": (14, 8),  "A6": (16, 11),
    "B1": (-1, 3),  "B2": (1, 6),   "B3": (4, 9),   "B4": (7, 9),   "B5": (11, 11), "B6": (16, 11),
    "C1": (12, 9),  "C2": (12, 5),  "C3": (12, 3),  "C4": (12, 0),  "C5": (16, 0),  "C6": (16, 3),
    "D1": (4, 9),   "D2": (4, 5),   "D3": (4, 3),   "D4": (4, -1),  "D5": (8, -1),  "D6": (8, 3)
}

# Line colors mapping
line_colors = {
    "Piccadilly": "blue",
    "Central": "red",
    "Northern": "black",
    "Jubilee": "grey"
}

# Draw Nodes by Line
for line_name, color in line_colors.items():
    nodes = [node for node, attr in G.nodes(data=True) if attr['line'] == line_name]
    nx.draw_networkx_nodes(G, pos, nodelist=nodes, node_color=color, node_size=100)

# Draw Edges by Line
nx.draw_networkx_edges(G, pos, edgelist=piccadilly_edges, edge_color=line_colors["Piccadilly"], width=2)
nx.draw_networkx_edges(G, pos, edgelist=central_edges, edge_color=line_colors["Central"], width=2)
nx.draw_networkx_edges(G, pos, edgelist=northern_edges, edge_color=line_colors["Northern"], width=2)
nx.draw_networkx_edges(G, pos, edgelist=jubilee_edges, edge_color=line_colors["Jubilee"], width=2)

# Custom Label List (Corrected Station Names & Clean Offsets)
station_labels = [
    ('Hyde Park Corner', (1, 0.4), {'ha': 'center', 'va': 'top'}),
    ('Green Park', (4, 5.5), {'ha': 'right', 'va': 'bottom'}),
    ('Piccadilly Circus', (8, 5.5), {'ha': 'center', 'va': 'bottom'}),
    ('Leicester Square', (12, 4.4), {'ha': 'right', 'va': 'top'}),
    ('Covent Garden', (14, 8.5), {'ha': 'right', 'va': 'bottom'}),
    ('Holborn', (16, 11.5), {'ha': 'center', 'va': 'bottom'}),
    ('Lancaster Gate', (-1, 2.4), {'ha': 'center', 'va': 'top'}),
    ('Marble Arch', (1, 6.5), {'ha': 'right', 'va': 'bottom'}),
    ('Bond Street', (3.8, 9.5), {'ha': 'right', 'va': 'bottom'}),
    ('Oxford Circus', (7, 9.5), {'ha': 'center', 'va': 'bottom'}),
    ('Tottenham Court Road', (11, 11.5), {'ha': 'center', 'va': 'bottom'}),
    ('Charing Cross', (12.5, 3), {'ha': 'left', 'va': 'center'}),
    ('Embankment', (12.5, 0), {'ha': 'left', 'va': 'center'}),
    ('Waterloo', (16.5, 0), {'ha': 'left', 'va': 'center'}),
    ('Kennington', (16.5, 3), {'ha': 'left', 'va': 'center'}),
    ('Westminster', (4, 2.4), {'ha': 'right', 'va': 'top'}),
    ('Southwark', (8, -1.5), {'ha': 'center', 'va': 'top'}),
    ('London Bridge', (8, 3.5), {'ha': 'center', 'va': 'bottom'})
]

# Style settings for clean text rendering without line overlap
bbox_style = dict(boxstyle="round,pad=0.2", fc="white", ec="none", alpha=0.85)

for name, (x, y), kwargs in station_labels:
    plt.annotate(name, xy=(x, y), fontsize=8.5, bbox=bbox_style, **kwargs)

# Draw Distance Edge Labels
edge_distances = {
    ('A1', 'A2'): '0.5 mi', ('A2', 'A3'): '0.4 mi', ('A3', 'A4'): '0.3 mi', ('A4', 'A5'): '0.2 mi', ('A5', 'A6'): '0.4 mi',
    ('B1', 'B2'): '0.8 mi', ('B2', 'B3'): '0.4 mi', ('B3', 'B4'): '0.3 mi', ('B4', 'B5'): '0.3 mi', ('B5', 'B6'): '0.4 mi',
    ('C1', 'C2'): '0.3 mi', ('C2', 'C3'): '0.3 mi', ('C3', 'C4'): '0.2 mi', ('C4', 'C5'): '0.5 mi', ('C5', 'C6'): '1.4 mi',
    ('D1', 'D2'): '0.6 mi', ('D2', 'D3'): '1.0 mi', ('D3', 'D4'): '0.7 mi', ('D4', 'D5'): '0.4 mi', ('D5', 'D6'): '0.9 mi'
}

nx.draw_networkx_edge_labels(G, pos, edge_labels=edge_distances, font_size=7, font_color='black', rotate=False)

# Title setup
plt.title("London Underground Map Network", fontsize=15, pad=20, fontweight='bold')

# Legend setup (Top-Left)
legend_handles = [
    plt.Line2D([0], [0], color='blue', marker='o', markersize=6, label='Piccadilly Line'),
    plt.Line2D([0], [0], color='red', marker='o', markersize=6, label='Central Line'),
    plt.Line2D([0], [0], color='black', marker='o', markersize=6, label='Northern Line'),
    plt.Line2D([0], [0], color='grey', marker='o', markersize=6, label='Jubilee Line')
]
plt.legend(handles=legend_handles, loc='upper left', frameon=True, fontsize=9)

# Canvas limits to ensure full visibility
plt.xlim(-3, 19)
plt.ylim(-3, 14)

# Hide axis ticks
plt.xticks([])
plt.yticks([])

plt.tight_layout()
plt.show()
