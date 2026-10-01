# Ion-channel wheel: data, assignments and references

Backs the ion-channel visualization on the site (`index.html`). Regenerate with `python3 tools/build_site.py && python3 tools/build_refs.py`.

## What the wheel shows

- **124 channels in 39 families**, in three rings: lineage (inner), family (middle), individual channel (outer). Names follow IUPHAR/HGNC conventions; gene symbols are HGNC.
- The wheel is a curated set of channels relevant to neurons and glia, **not** all ~400 human ion-channel genes (no auxiliary subunits, no CatSper, no ENaC, no CFTR, etc.). It deliberately omits aquaporin-4 (a water channel, not an ion channel) even though it is central to astrocyte endfeet.
- **Centre = schematic cladogram.** The voltage-gated-like (VGL) superfamily (Nav, Cav, TPC, TRP, HCN/CNG, Kv10–12, Kv, KCa, Kir, K2P) is drawn as one solid tree after Yu & Catterall (R1) and Yu et al. (R2); the other lineages (Cys-loop, iGluR, P2X, ASIC, gap-junction/large-pore, Piezo, TMEM16, bestrophin, ClC, Orai, Hv1) are **not** homologous to the VGL superfamily or to each other at this level and hang off the centre by dashed, unrooted spokes. Families are leaves; Nav, Kv1–Kv4, TRP and Kir are drawn as polytomies (relationships not resolved). Branch lengths are not to scale. Within-lineage pairings that *are* drawn: Cav1+Cav2 vs Cav3; Nav/NALCN sister to Cav; TPC (2×6TM) basal to the 4×6TM channels; HCN+CNG with KCNH (cyclic-nucleotide-binding domain); AMPA+kainate vs NMDA; pannexin+LRRC8. **This is a hand-built schematic, not a computed phylogeny; treat topology as illustrative.**

## How cell-type assignments were made

Each cell has 3–7 *territories* (subcellular regions). A channel is listed in a territory when a retrieved review or primary paper places it there (or, for glia, expresses it in that cell with the region as the best approximation). **A trailing `*` means approximate**: reported in that cell type in the general literature or textbook knowledge, but not individually confirmed in a source retrieved while building this page. Spatial placement for glia is coarser than for neurons: the glial reviews often say "soma and processes" without finer detail, so many glial channels appear in more than one territory. The aesthetic goal is a readable map, not a quantitative atlas.

### Neuron

| Territory | Channels | Key references |
|---|---|---|
| Soma | Kv2.1, Kv2.2, KCa3.1, Cav1.2*, Cav1.3*, GABA-A α1* | R3 |
| Proximal dendrite | Nav1.2, Nav1.6, KCa3.1, Kv2.1, Cav1.2*, Cav1.3*, Kv4.2*, Cx36*, GABA-A α1* | R3, R4, R5, R6 |
| Distal dendrite & spines | HCN1, HCN2*, Kv4.2, Kv4.3, KCa2.1, KCa2.2, Kir3.1, Kir3.2, Kir6.2, Nav1.2, Nav1.6, Cav3.1*, Cav3.2*, Cav2.3*, GluN1*, GluN2A*, GluN2B*, GluA1*, GluA2*, ASIC1a*, TRPV1* | R3, R4, R5, R7, R8 |
| Axon initial segment | Nav1.6, Nav1.2, Nav1.1*, Kv1.1, Kv1.2, Kv7.2, Kv7.3, Kv2.1, GABA-A α2* | R3, R6 |
| Node of Ranvier | Nav1.6, Kv7.2, Kv7.3, Kv3.1 | R3, R4 |
| Juxtaparanode | Kv1.1, Kv1.2 | R3 |
| Presynaptic terminal | Cav2.1*, Cav2.2*, Kv3.1, Kv3.2, Kv3.3, Kv3.4, Kv1.1, Kv1.4, Kv7.5, KCa1.1, HCN1, Cav3.2, nAChR α7* | R3, R9 |

### Astrocyte

| Territory | Channels | Key references |
|---|---|---|
| Soma | Nav1.5, Nav1.2, Nav1.3, Nav1.6, Kv1.1, Kv1.6, Kv3.4, Kv4.3, TREK1, TREK2, TWIK1, Kir6.2, Cav1.2*, GluA1*, GluN2C* | R10 |
| Main processes | Nav1.5, Nav1.2, Nav1.3, Nav1.6, Kv1.1, Kv1.6, Kv3.4, Kv4.3, TREK1, TREK2, TWIK1, Kir4.1, Kir5.1, TRPA1, Cx43, Cx30, Cx26*, LRRC8A, ClC-3*, Cav1.2*, GABA-A α1* | R10 |
| Fine perisynaptic processes | Kir4.1, Kir5.1, Best1, TRPA1, TRPV4, Orai1, nAChR α7, P2X7, Cx30, Panx1, LRRC8A, GluA1*, GluA2*, GluN2C*, ASIC1a* | R10 |
| Perivascular endfeet | Kir4.1, Kir5.1, KCa1.1, KCa3.1, KCa2.3*, Cx43, Cx30, TRPV4 | R10 |

### Microglia

| Territory | Channels | Key references |
|---|---|---|
| Soma | Kv1.3, Kv1.5, Kv1.1*, Kv1.2*, Kir2.1, KCa2.2, KCa2.3, KCa3.1, Orai1, Cav2.2*, nAChR α7*, Hv1* | R11, R12, R13 |
| Primary processes | THIK1, TWIK2*, Kv1.3*, Hv1, TRPM7, TRPV4*, Piezo1*, LRRC8A*, ClC-3*, P2X4, GluN1*, GluA2* | R11, R12, R14 |
| Ramified process tips | P2X4, P2X7, THIK1, TRPV4*, Piezo1*, Orai1*, ClC-3* | R11, R12 |

### Oligodendrocyte

| Territory | Channels | Key references |
|---|---|---|
| Soma | Kir4.1, Kv1.1, Nav1.1, Cav2.2, Cx47, Cx32, GluA2*, GluK2*, P2X7* | R15, R16, R18, R20 |
| Processes | GluN1, GluN2C, GluN3A, P2X7*, Kir4.1, Cx47* | R16, R19, R20 |
| Myelin internode | Cx47, Cx32, Cx29*, Kir4.1 | R16, R17, R18 |
| Paranodal loops & incisures | Cx32 | R18 |

### Notes on specific assignments (from retrieved sources)

- **Neuron, K⁺ channels:** Kv2.1/2.2 in large somatic clusters; Kv4.2/4.3, KCa2.1/2.2, Kir3.1/3.2 and Kir6.2 in distal dendrites/spines; Kv1.1/1.2 and Kv7.2/7.3 in the distal AIS; Kv7.2/7.3 and Kv3.1b at nodes; Kv1.1/1.2 at juxtaparanodes; Kv3.1–3.4, Kv1.1/1.4, Kv7.5 (calyx of Held) and KCa1.1 (mossy fibre) at terminals/preterminals (R3).
- **Neuron, Na⁺ channels:** Nav1.6 at the AIS and nodes and also in dendrites (R4); Nav1.2 enriched in the AIS and dendrites, Nav1.6 dominant at the AIS/nodes after myelination (R5, R6).
- **Neuron, HCN/Cav3:** HCN1 enriched in distal apical dendrites (≈60-fold somatic→distal immunogold gradient reported) (R7, R8); presynaptic HCN1 at asymmetric synapses regulating Cav3.2 (R9).
- **Astrocyte:** Kir4.1 enriched at perisynaptic processes and endfeet, Kir5.1 as partner; KCa (BK/IK/SK) mainly perivascular/endfeet; Nav1.2/1.3/1.5/1.6 and Kv1.1/1.6/3.4/4.3 in soma and processes; TRPA1/TRPV4 in fine-process Ca²⁺ activity; Best1 on perisynaptic processes; connexins Cx43/Cx30 and Panx1 (R10).
- **Microglia:** THIK-1 (K2P13.1) sets surveillance/resting potential; Kv1.3, KCa3.1, Kir2.1 are the three dominant K⁺ currents; Kv1.5 membrane (soma) and intracellular pools; P2X4/P2X7 purinergic; Hv1 is the CNS proton channel found predominantly in microglia; TRPM7/TRPV4 Ca²⁺ influx; Orai1 store-operated entry (R11–R14). The cited reviews give almost no subcellular (soma vs process) detail, so process/tip assignments are mostly `*`.
- **Oligodendrocyte lineage:** Kir4.1 throughout the lineage and required for K⁺ removal from the juxta-axonal space; Nav1.1, Cav2.2, Kv1.1 are Sox10 targets (R15, R16); Cx47 abundant on somata (coupled to astrocytic Cx43) and along internodal myelin, Cx32 at paranodes and Schmidt–Lanterman incisures (R17, R18); NMDA receptors (GluN1, GluN2C, GluN3A) mainly in processes, AMPA/kainate mainly on somata (R19, R20).

## Channel list by family

| Lineage | Family | Channels (gene) |
|---|---|---|
| Voltage-Gated 4×6Tm | Nav | Nav1.1 (SCN1A), Nav1.2 (SCN2A), Nav1.3 (SCN3A), Nav1.4 (SCN4A), Nav1.5 (SCN5A), Nav1.6 (SCN8A), Nav1.7 (SCN9A), Nav1.8 (SCN10A), Nav1.9 (SCN11A), Nax (SCN7A) |
| Voltage-Gated 4×6Tm | NALCN | NALCN (NALCN) |
| Voltage-Gated 4×6Tm | Cav1 | Cav1.1 (CACNA1S), Cav1.2 (CACNA1C), Cav1.3 (CACNA1D), Cav1.4 (CACNA1F) |
| Voltage-Gated 4×6Tm | Cav2 | Cav2.1 (CACNA1A), Cav2.2 (CACNA1B), Cav2.3 (CACNA1E) |
| Voltage-Gated 4×6Tm | Cav3 | Cav3.1 (CACNA1G), Cav3.2 (CACNA1H), Cav3.3 (CACNA1I) |
| Voltage-Gated 4×6Tm | TPC | TPC1 (TPCN1), TPC2 (TPCN2) |
| 6Tm Voltage-Gated-Like | TRPC | TRPC1 (TRPC1), TRPC3 (TRPC3), TRPC5 (TRPC5), TRPC6 (TRPC6) |
| 6Tm Voltage-Gated-Like | TRPV | TRPV1 (TRPV1), TRPV2 (TRPV2), TRPV3 (TRPV3), TRPV4 (TRPV4) |
| 6Tm Voltage-Gated-Like | TRPM | TRPM2 (TRPM2), TRPM3 (TRPM3), TRPM4 (TRPM4), TRPM7 (TRPM7), TRPM8 (TRPM8) |
| 6Tm Voltage-Gated-Like | TRPA | TRPA1 (TRPA1) |
| 6Tm Voltage-Gated-Like | HCN | HCN1 (HCN1), HCN2 (HCN2), HCN3 (HCN3), HCN4 (HCN4) |
| 6Tm Voltage-Gated-Like | CNG | CNGA1 (CNGA1), CNGA2 (CNGA2) |
| 6Tm Voltage-Gated-Like | Kv10–12 | Kv10.1 (KCNH1), Kv11.1 (KCNH2), Kv12.2 (KCNH3) |
| 6Tm Voltage-Gated-Like | Kv1 | Kv1.1 (KCNA1), Kv1.2 (KCNA2), Kv1.3 (KCNA3), Kv1.4 (KCNA4), Kv1.5 (KCNA5), Kv1.6 (KCNA6) |
| 6Tm Voltage-Gated-Like | Kv2 | Kv2.1 (KCNB1), Kv2.2 (KCNB2) |
| 6Tm Voltage-Gated-Like | Kv3 | Kv3.1 (KCNC1), Kv3.2 (KCNC2), Kv3.3 (KCNC3), Kv3.4 (KCNC4) |
| 6Tm Voltage-Gated-Like | Kv4 | Kv4.1 (KCND1), Kv4.2 (KCND2), Kv4.3 (KCND3) |
| 6Tm Voltage-Gated-Like | Kv7 | Kv7.1 (KCNQ1), Kv7.2 (KCNQ2), Kv7.3 (KCNQ3), Kv7.4 (KCNQ4), Kv7.5 (KCNQ5) |
| 6Tm Voltage-Gated-Like | KCa | KCa1.1 (KCNMA1), KCa2.1 (KCNN1), KCa2.2 (KCNN2), KCa2.3 (KCNN3), KCa3.1 (KCNN4) |
| 2Tm & K2P | Kir2 | Kir2.1 (KCNJ2), Kir2.2 (KCNJ12) |
| 2Tm & K2P | Kir3 | Kir3.1 (KCNJ3), Kir3.2 (KCNJ6) |
| 2Tm & K2P | Kir4/5 | Kir4.1 (KCNJ10), Kir5.1 (KCNJ16) |
| 2Tm & K2P | Kir6 | Kir6.2 (KCNJ11) |
| 2Tm & K2P | K2P | TWIK1 (KCNK1), TWIK2 (KCNK6), TREK1 (KCNK2), TREK2 (KCNK10), TRAAK (KCNK4), TASK1 (KCNK3), TASK3 (KCNK9), THIK1 (KCNK13) |
| Ligand-Gated | Cys-loop | GABA-A α1 (GABRA1), GABA-A α2 (GABRA2), GlyR α1 (GLRA1), nAChR α7 (CHRNA7) |
| Ligand-Gated | AMPA | GluA1 (GRIA1), GluA2 (GRIA2), GluA3 (GRIA3), GluA4 (GRIA4) |
| Ligand-Gated | Kainate | GluK1 (GRIK1), GluK2 (GRIK2) |
| Ligand-Gated | NMDA | GluN1 (GRIN1), GluN2A (GRIN2A), GluN2B (GRIN2B), GluN2C (GRIN2C), GluN3A (GRIN3A) |
| Ligand-Gated | P2X | P2X2 (P2RX2), P2X4 (P2RX4), P2X7 (P2RX7) |
| Ligand-Gated | ASIC | ASIC1a (ASIC1), ASIC2 (ASIC2) |
| Gap Junction & Large Pore | Connexin | Cx26 (GJB2), Cx29 (GJC3), Cx30 (GJB6), Cx32 (GJB1), Cx36 (GJD2), Cx43 (GJA1), Cx47 (GJC2) |
| Gap Junction & Large Pore | Pannexin | Panx1 (PANX1), Panx2 (PANX2) |
| Gap Junction & Large Pore | LRRC8 | LRRC8A (LRRC8A) |
| Other | Piezo | Piezo1 (PIEZO1), Piezo2 (PIEZO2) |
| Other | TMEM16 | TMEM16A (ANO1) |
| Other | Bestrophin | Best1 (BEST1) |
| Other | ClC | ClC-2 (CLCN2), ClC-3 (CLCN3) |
| Other | Orai | Orai1 (ORAI1) |
| Other | Hv1 | Hv1 (HVCN1) |

## References

All entries were checked against Crossref, Europe PMC or PubMed while building this page (title, authors, journal, year, DOI).

- **R1** Yu FH, Catterall WA. The VGL-chanome: a protein superfamily specialized for electrical signaling and ionic homeostasis. Science's STKE 2004;2004(253):re15. <https://doi.org/10.1126/stke.2532004re15>
- **R2** Yu FH, Yarov-Yarovoy V, Gutman GA, Catterall WA. Overview of molecular relationships in the voltage-gated ion channel superfamily. Pharmacol Rev 2005;57(4):387–395. PMID 16382097. <https://doi.org/10.1124/pr.57.4.13>
- **R3** Trimmer JS. Subcellular localization of K+ channels in mammalian brain neurons: remarkable precision in the midst of extraordinary complexity. Neuron 2015;85(2):238–256. <https://doi.org/10.1016/j.neuron.2014.12.042>
- **R4** Caldwell JH, Schaller KL, Lasher RS, Peles E, Levinson SR. Sodium channel Nav1.6 is localized at nodes of Ranvier, dendrites, and synapses. PNAS 2000;97(10):5616–5620. <https://doi.org/10.1073/pnas.090034797>
- **R5** Lorincz A, Nusser Z. Molecular identity of dendritic voltage-gated sodium channels. Science 2010;328(5980):906–909. <https://doi.org/10.1126/science.1187958>
- **R6** Liu H, Wang HG, Pitt G, Liu Z. Direct observation of compartment-specific localization and dynamics of voltage-gated sodium channels. J Neurosci 2022;42(28):5482–5496. <https://doi.org/10.1523/jneurosci.0086-22.2022>
- **R7** Shah MM. Cortical HCN channels: function, trafficking and plasticity. J Physiol 2014;592(13):2711–2719. <https://doi.org/10.1113/jphysiol.2013.270058>
- **R8** Tsay D, Dudman JT, Siegelbaum SA. HCN1 channels constrain synaptically evoked Ca2+ spikes in distal dendrites of CA1 pyramidal neurons. Neuron 2007;56(6):1076–1089. <https://doi.org/10.1016/j.neuron.2007.11.015>
- **R9** Huang Z, Lujan R, Kadurin I, Uebele VN, Renger JJ, Dolphin AC, Shah MM. Presynaptic HCN1 channels regulate Cav3.2 activity and neurotransmission at select cortical synapses. Nat Neurosci 2011;14(4):478–486. <https://doi.org/10.1038/nn.2757>
- **R10** Lia A, Di Spiezio A, Vitalini L, Tore M, Puja G, Losi G. Ion channels and ionotropic receptors in astrocytes: physiological functions and alterations in Alzheimer's disease and glioblastoma. Life 2023;13(10):2038. <https://doi.org/10.3390/life13102038>
- **R11** Stebbing MJ, Cottee JM, Rana I. The role of ion channels in microglial activation and proliferation – a complex interplay between ligand-gated ion channels, K+ channels, and intracellular Ca2+. Front Immunol 2015;6:497. <https://doi.org/10.3389/fimmu.2015.00497>
- **R12** Luo L, Song S, Ezenwukwa CC, Jalali S, Sun B, Sun D. Ion channels and transporters in microglial function in physiology and brain diseases. Neurochem Int 2021;142:104925. <https://doi.org/10.1016/j.neuint.2020.104925>
- **R13** Nguyen HM, Grössinger EM, Horiuchi M, Davis KW, Jin LW, Maezawa I, Wulff H. Differential Kv1.3, KCa3.1, and Kir2.1 expression in "classically" and "alternatively" activated microglia. Glia 2017;65(1):106–121. <https://doi.org/10.1002/glia.23078>
- **R14** Wu LJ. Voltage-gated proton channel HV1 in microglia. Neuroscientist 2014;20(6):599–609. <https://doi.org/10.1177/1073858413519864>
- **R15** Peters C, Aberle T, Sock E, Brunner J, Küspert M, Hillgärtner S, Wegner M, et al. Voltage-gated ion channels are transcriptional targets of Sox10 during oligodendrocyte development. Cells 2024;13(13):1159. <https://doi.org/10.3390/cells13131159>
- **R16** Schirmer L, Möbius W, Zhao C, Cruz-Herranz A, Ben Haim L, et al. Oligodendrocyte-encoded Kir4.1 function is required for axonal integrity. eLife 2018;7:e36428. <https://doi.org/10.7554/elife.36428>
- **R17** Menichella DM, Majdan M, Awatramani R, Goodenough DA, Sirkowski E, Scherer SS, Paul DL. Genetic and physiological evidence that oligodendrocyte gap junctions contribute to spatial buffering of potassium released during neuronal activity. J Neurosci 2006;26(43):10984–10991. <https://doi.org/10.1523/jneurosci.0304-06.2006>
- **R18** Kamasawa N, Sik A, Morita M, Yasumura T, Davidson KGV, Nagy JI, Rash JE. Connexin-47 and connexin-32 in gap junctions of oligodendrocyte somata, myelin sheaths, paranodal loops and Schmidt–Lanterman incisures. Neuroscience 2005;136(1):65–86. <https://doi.org/10.1016/j.neuroscience.2005.08.027>
- **R19** Káradóttir R, Cavelier P, Bergersen LH, Attwell D. NMDA receptors are expressed in oligodendrocytes and activated in ischaemia. Nature 2005;438:1162–1166. <https://doi.org/10.1038/nature04302>
- **R20** Káradóttir R, Attwell D. Neurotransmitter receptors in the life and death of oligodendrocytes. Neuroscience 2007;145(4):1426–1438. <https://doi.org/10.1016/j.neuroscience.2006.08.070>

## Caveats

- Channel names/genes were written from standard nomenclature; the IUPHAR/BPS Guide to Pharmacology site could not be retrieved in the build session, so nomenclature is not cross-checked against it.
- Several textbook-level facts (e.g., Nav1.1 at interneuron AIS, Cav2.1/2.2 at presynaptic active zones, ASIC1a in spines, GABA-A α2 at the AIS) are marked `*` and should be verified before being cited elsewhere.
- The brain is species- and development-dependent (e.g., Nav1.2→Nav1.6 switch with myelination; microglial Kv1.3/KCa3.1/Kir2.1 change with activation; human vs rodent differences). The map is a composite.
- Not a clinical or quantitative resource.
