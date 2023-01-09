import datetime

d = ('Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday')
ms = ('January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December')
print('Calendar generator')

while True:
    print('Enter the year: ')
    res = input('> ')

    if res.isdecimal() and int(res) > 0:
        year = int(res)
        break
    print('Enter the year as a numerical value, e.g. 2001 ')
    continue

while True:
    print('Enter the month, 1-12: ')
    res = input('> ')
    if not res.isdecimal():
        print('Enter the month as a numerical value, e.g. 5 for May ')
        continue

    m = int(res)
    if 1 <= m <= 12:
        break
    print('Enter number from 1 to 12.')

def getCalendar(y, m):
    cText = ''

    cText += (' ' * 34) + ms[m - 1] + ' ' + str(y) + '\n'
    cText += '   Sunday     Monday    Tuesday    Wednesday   Thursday   Friday    Saturday \n'
    sep = ('+----------' * 7) + '+\n'
    row = ('|          ' * 7) + '|\n'

    currDate = datetime.date(y, m, 1)
    while currDate.weekday() != 6:
        currDate -= datetime.timedelta(days=1)

    while True:
        cText += sep

        dayNumRow = ''
        for i in range(7):
            dayNumLabel = str(currDate.day).rjust(2)
            dayNumRow += '|' + dayNumLabel + (' ' * 8)
            currDate += datetime.timedelta(days=1)
        dayNumRow += '|\n'

        cText += dayNumRow
        for i in range(3):
            cText += row
        if currDate.month != m:
            break

    cText += sep
    return cText

cText = getCalendar(year, m)
print(cText)

calFName = 'kalendarz {}_{}.txt'.format(year, m)
with  open(calFName, 'w') as fileObj:
    fileObj.write(cText)

print('Saved with name ' + calFName)
