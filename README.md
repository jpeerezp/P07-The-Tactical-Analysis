# P07 · The Tactical Analysis

**Section:** 02 - The High-Performance Microcycle

**Workflow step:** Step 3 of 4

**Current version:** v1.0

**Status:** ✅ Tested and approved

**Last updated:** March 2026

---

## 📌 Prompt Text (v1.0 — current)

```
Role: You are the Lead Tactical Analyst and Squad Logistics Coordinator for an elite European football club.

Action: Conduct a "Tactical Feasibility Analysis" for the MD+3 session. Synthesize P03 Tactical Pillar requirements with P06 Readiness Convergence constraints. 
Return in JSON format.

Context: Today is the peak tactical day (72h post-match). We are in a 5-day congestion window. We must map our "Ideal Game Model" (P03) against the "Physical/Neural Reality" (P06) to decide if our tactical plan for the next opponent is logistically viable for the available squad.

Inputs:
- P03 Tactical Pillar: "technical_tactical_readiness_report" 
- P06 Readiness Report: "readiness_convergence_md_plus_2" 
- Opponent Tactical Profile: 
{
  "opponent_id_profile": "ATLETICO_MADRID",
  "tactical_analysis": {
    "primary_formation": "3-2-4-1 (In Possession)",
    "defensive_structure": "5-4-1 Mid-Block",
    "attacking_style": "Vertical Tik-Taka",
    "key_metrics": {
      "average_possession": "58.4%",
      "ppda": 8.2,
      "field_tilt": "62.1%",
      "expected_goals_against_per_90": 0.88
    },
    "tactical_nuances": {
      "build_up": "Inverted fullbacks creating a central box-four to overload the midfield pivot.",
      "defensive_trans": "Aggressive counter-press triggered by the loss of possession in the half-spaces.",
      "offensive_threat": "High-frequency overlapping runs from the wide-center-backs during sustained pressure."
    },
    "vulnerabilities": {
      "primary_weakness": "Space vacated behind wing-backs during rapid transitions.",
      "secondary_weakness": "Susceptibility to direct diagonal long balls targeting the 'blind-side' of the lateral center-backs."
    },
    "set_piece_profile": {
      "corners": "Near-post flick-on specialization",
      "defensive_free_kicks": "High defensive line, utilizing an offside trap."
    }
  },
  "sports_science_insights": {
    "physical_load_prediction": "High metabolic power requirement due to opponent's constant lateral shifting.",
    "sprint_volume_expected": "Above 2,500m (Team Total) due to recovery runs required in transition.",
    "recommended_taper": "48-hour neural priming focus; reduced eccentric loading in Match-Day -2."
  }
}

Logic & Logistics Matrix:
1. Positional Stress Match: Cross-reference P03 "High-Workload Zones" with P06 "Yellow/Red" players. 
   - IF the game plan requires High-Speed Overlaps BUT the Full-Backs are "Modified" -> FLAG: "Positional Logistic Failure."
2. Strategic Pivot: If >3 core starters (ID 824001-824011) are capped at <70% intensity, suggest a "Tactical Compromise" (e.g., Mid-block instead of High-press).
3. Space Compression: If squad SRI (Squad Readiness Index) is < 75%, automatically prescribe reduced pitch dimensions for drills to limit total distance while maintaining tactical repetitions.

Constraints:
- Tone: Highly strategic, objective, and solution-oriented.
- JSON must include a "Strategic Risk Rating" (1-10).
Tactical Logistics Analysis (JSON):
{
  "md_plus_3_logistics": {
    "strategic_risk_rating": [1-10],
    "tactical_viability": {
      "original_intent": "[e.g., Vertical Tiki-Taka / High-Press]",
      "feasibility_score": "[%]",
      "bottleneck_positions": ["[pos]"]
    },
    "prescribed_session_adjustments": {
      "drill_format": "[e.g., 8v8 on 40m pitch]",
      "intensity_instruction": "[e.g., Tactical walk-through vs. Live speed]",
      "load_management_fix": "[Specific instruction to protect Yellow Light players]"
    },
    "projected_starting_xi_viability": "[High / At Risk / Low]"
  }
}
```

**Placeholders to Fill:**

| Placeholder | Source | Example |
| :--- | :--- | :--- |
| `[tactical_readiness_report]` | JSON output from `P03` (Ideal tactical blueprint). | `{ "pressing_triggers": "High", "width": 85... }` |
| `[readiness_convergence]` | JSON output from `P06` (Green/Yellow/Red status). | `{ "player_id": 824006, "status": "Green"... }` |
| `[opponent_id_profile]` | Detailed scouting report (e.g., Atletico Madrid). | `{ "formation": "4-4-2", "low_block": true... }` |
| `[session_duration_min]` | Total duration of the field session in minutes. | `90` |

---

## 🏢 Intended Workflow or Task

This prompt acts as the **"Strategic Mediator"**. It resolves the natural tension between the Head Coach’s tactical ambition and the Sports Science department's physical constraints.

**Trigger:** `MD+3` Morning (72 hours post-match), once the `P06` Convergence report is finalized.

**Actor:** Lead Tactical Analyst &nbsp; • &nbsp; Head of Sports Science.

**Timing:** Pre-training "War Room" meeting on the peak tactical day.

**Next step:** `P08` — The Traveling 16 (where logistic viability determines the final roster).

```
P03 (Tactical Blueprint) + P06 (Physio Clearance) → [P07 Strategic Mediator] 
  ↳ [OUTPUT] → Drill Dimensions (m²) 
  ↳ [OUTPUT] → High-Speed Running (HSR) Targets per drill
  ↳ [OUTPUT] → Tactical Role Assignment (Full vs. Neutral)
```

---

## ❗ Problem Being Solved: 

The **"Tactical-Physical Gap"** occurs when a coach designs a high-intensity session (e.g., 11v11 full-pitch pressing) without realizing the squad's metabolic power is depleted from a congested 5-day cycle. `P07` bridges this gap by aligning the "Ideal Game" with the "Available Engine."

**Pain Points Addressed:**

- Strategic Failure Prevention: Prevents the team from practicing a tactic they are physically too fatigued to execute. Practicing "High Press" with depleted glycogen stores leads to poor synchronization, creating negative muscle memory for the actual matchday.

- Automated Drill Scaling: Automatically adjusts the "Physical Dimensions" of drills. If `P06` flags systemic fatigue, `P07` scales the exercise (e.g., moving from a 105m pitch to a 40m box). This ensures tactical learning (positioning/triggers) occurs while eliminating the high-speed running (HSR) injury risk.

---

## ⚡ Automation Potential: 

**Overall Level:** `High`

This prompt performs an Automated Gap Analysis. It calculates the "Tactical Cost" of the Game Model against the "Biological Budget" of the filtered squad.

**Strategic Viability Formula:**

$$V_{strat} = \frac{\sum (P_{ready} \cdot I_{cap})}{\sum (T_{demand})}$$

| Variable | Definition |
| :--- | :--- |
| $V_{strat}$ | **Viability Score:** The probability of tactical success without injury risk. |
| $P_{ready}$ | **Cleared Players:** Total count of "Green Light" athletes from `P06`. |
| $I_{cap}$ | **Intensity Limit:** The individual metabolic ceiling for the session. |
| $T_{demand}$ | **Tactical Requirement:** The physical load demanded by the Coach's drill. |


**Gap Identification:** If $V_{strat} < 0.85$, the prompt automatically generates a **"Modification Protocol"**, reducing pitch dimensions or adding "Neutral" players to lower the $T_{demand}$.

**Data Integration:** High-speed mapping from `P03` (Tactics) and `P06` (Physio) eliminates 2 hours of manual "War Room" negotiation.

**Outcome:** Instant generation of a **Drill-Specific Load Sheet** for the GPS Analyst.

**Estimated time saving:** ~75% (Automated alignment between physical capacity and tactical ambition).

---

## ⚠️ Risks and Limitations: 

| Risk | Level | Mitigation |
| :--- | :---: | :--- |
| **Coaching Veto** | `High` | Frame the "Tactical Compromise" as a way to **increase the chance of winning**, rather than just a way to rest players. |
| **Static Scouting** | `Medium` | Ensure the `[opponent_id_profile]` is updated with the most recent 3 matches to account for their own potential rotation. |
| **Logic Conflict** | `Low` | If `P03` and `P06` are fundamentally incompatible, `P07` must force a **"Tactical Pivot"** (e.g., dropping to a Low Block). |

**Overall Risk Rating:** `MEDIUM-HIGH` - The technical accuracy is high, but the "Coaching Veto" represents a significant cultural barrier. Success depends on the Analyst's ability to present data as "Performance Optimization" rather than "Medical Restriction."

---

### v1.0 - Tactical Masterclass ✅ Current

**Date:** March 18 2026

**Output:** 

```
{
  "md_plus_3_logistics": {
    "strategic_risk_rating": 8,
    "squad_readiness_index": {
      "calculation": {
        "core_starters_assessed": ["824001","824002","824003","824004","824005","824006","824007","824008","824009","824010","824011"],
        "convergence_scores": [94, 38, 62, 60, 28, 18, 12, 16, 42, 44, 68],
        "average_sri": 44.0
      },
      "sri_threshold_breach": true,
      "sri_verdict": "CRITICAL — Squad SRI (44.0%) is catastrophically below the 75% threshold. Automatic pitch compression protocol activated."
    },
    "tactical_viability": {
      "original_intent": "Vertical Tiki-Taka / High-Press Counter with High-Speed Full-Back Overlaps and Midfield Overload",
      "feasibility_score": "21%",
      "bottleneck_positions": ["CM (824007, 824008)", "CDM (824006)", "LB (824005)", "RB (824002)"],
      "positional_logistic_failures": [
        {
          "flag": "POSITIONAL LOGISTIC FAILURE — FULL-BACKS",
          "detail": "Game model requires high-speed overlapping runs from RB (824002, convergence 38, Yellow) and LB (824005, convergence 28, Red). Both are capped at 60% / 0% intensity respectively. Opponent's primary vulnerability — space behind wing-backs in transition — is INACCESSIBLE with current full-back readiness. Exploitation of this channel is not logistically viable with first-choice personnel."
        },
        {
          "flag": "POSITIONAL LOGISTIC FAILURE — MIDFIELD ENGINE",
          "detail": "Both box-to-box CMs (824007, convergence 12, Red; 824008, convergence 16, Red) and CDM (824006, convergence 18, Red) are on full pitch exclusion. The three-man midfield core responsible for high-frequency pressing triggers, packing, and inter-line movements is entirely unavailable for tactical integration. Squad's median packing rate in midfield (65–82 in matchday data) cannot be replicated. Counter-press shape against Atletico's vertical build-up is structurally non-functional."
        },
        {
          "flag": "POSITIONAL LOGISTIC FAILURE — HIGH-PRESS SYSTEM",
          "detail": "Strategic Pivot Threshold breached: 7 of 11 core starters (824002, 824003, 824004, 824005, 824006, 824007, 824008) are capped below 70% intensity. This exceeds the >3 threshold by +4. High-press system is inoperative. Mandatory Tactical Compromise protocol engaged."
        }
      ]
    },
    "strategic_pivot": {
      "trigger": "7 core starters below 70% intensity threshold — mandatory tactical compromise activated",
      "original_system_abandoned": "High-Press / Vertical Tiki-Taka with Full-Back Overlaps",
      "prescribed_compromise": "Compact Mid-Block (4-4-2 / 4-5-1 Defensive Shape) with Rapid Vertical Counter on Turnover",
      "rationale": [
        "Eliminates high metabolic power demand incompatible with current squad state",
        "Reduces sprint volume requirement from opponent-projected 2,500m+ to sub-1,800m team total",
        "Leverages secondary opponent weakness: diagonal long balls to blind-side of lateral CBs — executable with reduced physical output from ST (824010) and available wingers",
        "Protects Red-light midfielders from tactical workload while reserve CDM (824018, convergence 96) and CM (824012, convergence 88) absorb tactical repetitions at full intensity",
        "Defensive compactness scores for available Green-light defenders (824016: est. 94%+, 824022: est. 96%+) support mid-block integrity without first-choice CB dependency"
      ]
    },
    "space_compression_protocol": {
      "triggered": true,
      "trigger_reason": "SRI 44.0% — below 75% automatic threshold",
      "prescribed_dimensions": "Reduced pitch: 35m x 28m (from standard 68m x 40m tactical format)",
      "drill_rationale": "Compressed dimensions maintain tactical shape repetitions, pressing lane recognition, and combination patterns while capping total distance covered per player. High spatial density replicates Atletico's 5-4-1 mid-block compactness without requiring sprint-distance output."
    },
    "prescribed_session_adjustments": {
      "drill_format": "6v6 + 2 neutral targets on 35m x 28m pitch — positional shape and transition triggers only. Set-piece rehearsal (diagonal delivery to blind-side CB zone) in static and semi-live format.",
      "intensity_instruction": "Tactical walk-through to 60% live speed maximum. No live pressing sequences above jogging pace. All transition triggers executed at controlled tempo. Zero plyometric or sprint-above-25km/h content.",
      "load_management_fix": {
        "red_light_players": {
          "824005": "Full pitch exclusion maintained. No change from MD+2 prescription. Sleep hygiene and manual therapy priority.",
          "824006": "Full pitch exclusion maintained. Physio sign-off still required. Passive indoor recovery only.",
          "824007": "Full pitch exclusion maintained. Anti-inflammatory protocol adherence mandatory. Medical staff daily review continues. No tactical integration until minimum 70% recovery confirmed.",
          "824008": "Full pitch exclusion maintained. Compression and cryo protocol continues. No eccentric loading."
        },
        "yellow_light_players": {
          "824002": "Aerobic base walk-through only within compressed drill format. No directional change demands. HRV trend must be reviewed before clearance to participate even at reduced intensity.",
          "824003": "Positional shape work permitted at 60% within compressed drill. No aerial content. Active recovery (P06) to run concurrently around session.",
          "824004": "Possession-retention patterns only at 60%. No physical duels simulated. Nutritional repletion confirmed before participation.",
          "824009": "Wide corridor pattern recognition at 60% — walking pace transitions only. Pool recovery session replaces any post-drill conditioning.",
          "824010": "Pressing movement walk-through only. No explosive acceleration triggers. Manual therapy confirmed post-session. Nutritional repletion pre-clearance mandatory.",
          "824011": "Technical wide combination drills at 60%. No repeated acceleration bouts. Candidate for Green clearance at MD+4 if HRV stabilises — protect toward matchday."
        },
        "green_light_reserves_integration": {
          "instruction": "Full-intensity tactical unit work delegated to Green-light reserves (824012, 824013, 824014, 824015, 824016, 824017, 824018, 824019, 824021, 824022). These players absorb all high-intensity tactical repetitions, set-piece rehearsal, and pressing shape drills at 100% load.",
          "specific_roles": {
            "824016": "Integrate at CB in first-choice defensive shape — cover for Red-light CB absence.",
            "824022": "Pair with 824016 as CB unit — eligible for aerial duel and physical contact drills.",
            "824018": "CDM tactical shape lead — absorb all pressing trigger repetitions at full intensity.",
            "824021": "Wide channel exploitation drills — rehearse diagonal transition runs targeting opponent wing-back space. Primary cover for Red/Yellow winger absence.",
            "824017": "LB role integration — full-intensity overlap and recovery run rehearsal. Cover for Red-light 824005.",
            "824015": "Goalkeeper high-pressure and distribution sets at 100% — integrate into all transition drills."
          }
        }
      }
    },
    "projected_starting_xi_viability": {
      "verdict": "LOW",
      "detail": "First-choice XI as deployed in Matchday 1 is not viable for Matchday 2. Four players (824006, 824007, 824008, 824005) remain on full pitch exclusion with no confirmed clearance pathway before matchday. A minimum of 4 starting positions require personnel changes. Green-light reserves (824016, 824017, 824018, 824021, 824022) provide positionally compatible cover but represent a significant reduction in established combination chemistry and technical tactical metrics relative to first-choice profiles.",
      "forced_rotation_positions": ["LB (824005 → 824017)", "CDM (824006 → 824018)", "CM (824007 → 824012 or 824019)", "CM (824008 → 824012 or 824019)"],
      "conditional_recoveries": {
        "824002": "Potential matchday availability if HRV trend recovers to ≥60 by MD+4 morning check.",
        "824011": "Strong candidate for Green clearance at MD+4 — protect and monitor. Do not overload at MD+3.",
        "824003": "Matchday availability marginal — dependent on recovery trajectory. Low-risk positional cover likely required."
      },
      "set_piece_opportunity": "Diagonal long ball delivery targeting Atletico blind-side lateral CB remains executable with available Green-light personnel. Recommend prioritising this rehearsal at MD+3 as primary offensive set-piece vehicle — low physical demand, high strategic dividend against this opponent profile."
    }
  }
}
```

**Observed effect:** By forcing "Space Compression" (smaller pitch dimensions) during MD+3 tactical sessions, the club saw a significant drop in "Third-Day Fatigue" spikes during the 5-day cycle.

**Note**: As of MD+3 we still have a few starting players with no confirmed clearance pathway before matchday. P08 will give defitiive clearence for those who followed a successfull recovery based on (P05) proposed solution.

---

## 📊 v1.0 Test Results: 

| Criteria | Score | Evaluation & Status Summary |
| :--- | :---: | :--- |
| **Readability** | `5.0 / 5` | `✅ Tactical and physical data synced.` |
| **Completeness** | `5.0 / 5` | `✅ All drill scaling logic validated.` |
| **Tone Appropriateness** | `5.0 / 5` | `✅ Persuasive and performance-driven.` |
| **Instruction Adherence** | `5.0 / 5` | `✅ Viability formula ($V_{strat}$) applied.` |
| **Data Structuring** | `5.0 / 5` | `✅ JSON outputs are drill-ready.` |
| **Send-ready Status** | `5.0 / 5` | `✅ Zero manual negotiation required.` |
| **Overall Performance** | **`5.0 / 5`** | ⭐ **Gold Standard** |

**😁 Mastering the promping at this stage**
