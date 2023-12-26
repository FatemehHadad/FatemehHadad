def sort_list(lst):
    if len(lst) <= 2:
        return sorted(lst)
    
    m = len(lst) // 3
    first_part = sort_list(lst[:m])
    second_part = sort_list(lst[-m:])
    third_part = sort_list(lst[m:-m])
    
    if first_part[-1] > second_part[0]:
        first_part, second_part = second_part, first_part
    
    if second_part[-1] > third_part[0]:
        second_part, third_part = third_part, second_part
    
    return first_part + second_part + third_part

