#17.9.1

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
    try:
        element = int(input("Введите любое целое число: "))
        if element < 0 or element > 999:
            raise Exception
        break
    except ValueError:
        print("Ведите число!")
    except Exception:
        print("Неправильный диапазон!")

array = [i for i in range(1, 1000)]

num = list(map(int, input("Введите целые числа через пробел:").split()))

num.append(element)
print(sorted(num))


index = num.index(element)

print('Индекс введенного элемента:', element, 'в списке равен:', index)
print('индекс элемента слева')
print(binary_search(array, element, 0, 999))
