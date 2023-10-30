def arithmetic_arranger(problems, val=False):
    arranged_solutions = ''
    if len(problems) > 5:
        return 'Error: Too many problems.'

    operation = list(map(lambda x: x.split()[1], problems))

    if set(operation) != {'+', '-'} or set(operation) != {'-', '+'}:
        return "Error: Operator must be '+' or '-'."

    numbers = []

    for i in problems:
        problem = i.split()
        numbers.extend([problem[0], problem[2]])

    for i in numbers:
        if i.isdigit() == False:
            return 'Error: Numbers must only contain digits.'

    if not all(map(lambda x: len(x) < 5, numbers)):
        return "Error: Numbers cannot be more than four digits."

    top_line = ''
    dashes = ''
    result = list(map(lambda x: eval(x), problems))
    solutions = ''

    for i in range(0, len(numbers), 2):
        space_width = max(len(numbers[i]), len(numbers[i + 1])) + 2
        top_line += numbers[i].rjust(space_width)
        dashes += '-' * space_width
        solutions += str(result[i // 2]).rjust(space_width)
        if i != len(numbers) - 2:
            top_line += ' ' * 4
            dashes += ' ' * 4
            solutions += ' ' * 4

    bottom_line = ''
    for i in range(1, len(numbers), 2):
        space_width = max(len(numbers[i - 1]), len(numbers[i])) + 1
        bottom_line += operation[i // 2]
        bottom_line += numbers[i].rjust(space_width)
        if i != len(numbers) - 1:
            bottom_line += ' ' * 4

    if val:
        arranged_solutions = '\n'.join((top_line, bottom_line, dashes, solutions))
    else:
        arranged_solutions = '\n'.join((top_line, bottom_line, dashes))

    return arranged_solutions

