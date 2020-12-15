import requests
import argparse
import json
from bs4 import BeautifulSoup
from urllib3 import disable_warnings
from time import time
from urllib3.exceptions import InsecureRequestWarning

disable_warnings(InsecureRequestWarning)
disable_warnings(InsecureRequestWarning)

session = requests.Session()


def argParse():
    parser = argparse.ArgumentParser()
    parser.add_argument("itemID")
    args = parser.parse_args()
    return args.itemID


def login():
    print('Log In...')
    headers = {
        "authority": "shopee.co.id",
        "path": "/api/v2/authentication/login",
        "scheme": "https",
        "accept": "application/json",
        "accept-encoding": "gzip, deflate, br",
        "accept-language": "en,en-US;q=0.9",
        "cache-control": "no-cache",
        "content-type": "application/json",
        "if-none-match-": "55b03-96f20d3a1457c2cbdccc6836c77b6d37",
        "origin": "https://shopee.co.id",
        "pragma": "no-cache",
        "referer": "https://shopee.co.id/",
        "sec-fetch-dest": "empty",
        "sec-fetch-mode": "cors",
        "sec-fetch-site": "same-origin",
        "x-api-source": "pc",
        "x-csrftoken": 'u3SXW8YxuSTvrFJXo2etv28BVmahWYsr',
        "x-requested-with": "XMLHttpRequest",
        "user-agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.122 Safari/537.36",
        'referer': 'https://shopee.co.id/',
        'Cookie': '_gcl_au=1.1.1834471157.1585507223; _fbp=fb.2.1585507224020.14904287; csrftoken=u3SXW8YxuSTvrFJXo2etv28BVmahWYsr; SPC_IA=-1; REC_T_ID=c1a26b6c-71ec-11ea-8b52-d0946614bb47; SPC_F=wgqyx5Brvbk01wt1kYDtiYeLLikiEDEB; REC_T_ID=c1c5d526-71ec-11ea-9662-40eeddd2d365; welcomePkgShown=true; _ga=GA1.3.1905306069.1585507227; _gid=GA1.3.1102905196.1585507227; G_ENABLED_IDPS=google; CTOKEN=SwUwy3HuEeqREvBj%2BRgSzg%3D%3D; AMP_TOKEN=%24NOT_FOUND; SPC_SI=vf54ia7m69qqv31hrfbxn72ar7o5545m; SPC_U=-; SPC_EC=-; REC_MD_20=1585591735; REC_MD_14=1585591898; REC_MD_30_2001304014=1585591826; _dc_gtm_UA-61904553-8=1; REC_MD_41_1000044=1585592031_0_50_0_47; SPC_R_T_ID="v0ek3k+H6MGb+HugLskxIfX3ITiZepYvNHojn9T71hpWuYDuOi7rPNf7x1lt9qhdEnwijBkQzL+HXckxrg0s8nMKxl203GV23mx138JDivw="; SPC_T_ID="v0ek3k+H6MGb+HugLskxIfX3ITiZepYvNHojn9T71hpWuYDuOi7rPNf7x1lt9qhdEnwijBkQzL+HXckxrg0s8nMKxl203GV23mx138JDivw="; SPC_R_T_IV="92RJVhF9KcqMZoN9hKmuzQ=="; SPC_T_IV="92RJVhF9KcqMZoN9hKmuzQ=="'
    }
    landing_url = 'https://shopee.co.id/'
    landing_res = session.get(landing_url, headers=headers)
    if landing_res.status_code != 200:
        return False
    cart_url = 'https://shopee.co.id/api/v1/account_info/?need_cart=1&skip_address=1'

    get_res = session.get(cart_url, headers=headers, verify=False)
    recommend_url = 'https://shopee.co.id/api/v2/recommendation/hot_search_words?limit=8&offset=0'
    recommend_res = session.get(recommend_url, headers=headers, verify=False)
    if get_res.status_code == 200 and recommend_res.status_code == 200:
        post_data = {
            "password": "5578b76d12a0eac49966b8840465784286f1babaf26a8ae47ac14c861597f7d9",
            "captcha": "",
            "support_whats_app": True,
            "username": "kideveloper612"
        }
        login_url = 'https://shopee.co.id/api/v2/authentication/login'
        post_res = session.post(login_url, headers=headers, data=post_data, allow_redirects=True, verify=False)
        print(post_res.status_code)
        if post_res.status_code == 403:
            print('Incorrect email or password')
            return False
        else:
            print('Sucessful Login')
            session.get('https://www.instagram.com/', verify=False)
            return True
    else:
        return False


def autoBuy():
    ID = argParse()
    initial_url = 'https://shopee.co.id/product/{}'.format(ID)
    login_result = login()
    if login_result:
        print('Success')
    else:
        print('Failed')


if __name__ == "__main__":
    autoBuy()
