Python的['str1'] + ['str2']会是['str1', 'str2']。['str1'] + 'str2'会是['str1', 's', 't', 'r', '2']

Python的字典的value如果是一个列表，比如['str1', 'str2]，那么想取['str1']就是dict[key][0:1]，想取'str1'就是dict[key][0]
