import time
import hashlib
import logging
list_of_charchter = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'a', 'b', 'c', 'd', 'e', 'f', 'g',
                         'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x',
                         'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O',
                         'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z', '!', ';', ':', '_']


def generate_password(size):
    password_num = []
    password = []
    num = ""
    while len(password_num) < size:
        if num != str("%.20f" % time.time()):
            num = str("%.20f" % time.time())[-2:]
            if int(num) <= len(list_of_charchter):
                password_num.append(num)
                num = str("%.20f" % time.time())
    for i in range(size):
        password.append(list_of_charchter[int(password_num[i])])
    password = "".join(password)
    return (password)

def login():

    my_password_sha256 = "4b18f96c61620785985b7a8a79f80a98340b4ec8822f5cdebea9303d98941b77"
    inputted_password = input("password\n")
    hash_object = hashlib.sha256(inputted_password.encode('utf-8'))

    if hash_object.hexdigest() == my_password_sha256:
        print("successful")
        while True:
            taken_input = input("1: Generate a random password\n2: Read a password")
            if taken_input == "1":
                len = int(input("Length?"))
                password = generate_password(len)
                my_passwords = open("passwords.txt", "w")
                my_passwords.write(password)
                print(password)
            if taken_input == "2":
                my_passwords = open("passwords.txt", "r")
                flist_of_hashes = my_passwords.readlines()
                list_of_hashes = []
                for i in flist_of_hashes:
                    list_of_hashes.append(i[:-1])
                for i in list_of_hashes():
                    print(list_of_hashes)


login()
