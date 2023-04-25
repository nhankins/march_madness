# march_madness

Entered Kaggle Competition to use machine learning in predicting the march madness 2023 season results


Misc:

This For Loop should be able to strip the unnecessary seed info via regex

for x in range(len(tourney_input)):
    idx = (tourney_input['Season'][x], tourney_input['Team1'][x])
    try:
        seed = seed_dict.loc[idx].values[0]
    except KeyError:
        pass
    
    stripped_seed = re.search('\w(\d+)\w?', seed)
    if stripped_seed:
        found = stripped_seed.group(1)

    team1seeds.append(found)
