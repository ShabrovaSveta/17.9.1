def sort_num(array):
    for i in range(len(array)):
        for j in range(len(array) - i - 1):
            if array[j] > array[j + 1]:
                array[j], array[j + 1] = array[j + 1], array[j]
    return array


def binary_search(array, element, left, right):
    if left > right:
        return False
    middle = (right + left) // 2
    if array[middle] == element:
        return middle
    elif element < array[middle]:
        return binary_search(array, element, left, middle - 1)
    else:
        return binary_search(array, element, middle + 1, right)


while True:
    num_srt = input('Введите последовательность чисел через пробел: ')
    num_val = input('Введите целое число: ')
    try:
        list_of_numbers = [int(x) for x in num_srt.split() if x]
        if not list_of_numbers:
            raise ValueError()
        value = int(num_val)
        break
    except ValueError as e:
        print('Ввод содержит недопустимые символы')

sort_list = sort_num(list_of_numbers)
print(sort_list)

if value < sort_list[0] or value > sort_list[-1]:
    print('Введенное число отсутствует в массиве')
elif value == sort_list[0] and len(sort_list) == 1:
    print('Введеное число равно единственному элементу массива')
elif value == sort_list[0]:
    print('Введеное число равно первому элементу массива')
elif value == sort_list[-1]:
    print('Введеное число равно последнему элементу массива')
else:
    list_of_numbers.append(value)
    sort_list = sort_num(list_of_numbers)
    # print(f'* sort_list = {sort_list}')
    found_index = binary_search(sort_list, value, 0, len(sort_list) - 1)
    print(f'Индекс элемента меньше чем введеное число = {found_index - 1}')
    print(f'Индекс элемента больше/равно введенному числу = {found_index}')
