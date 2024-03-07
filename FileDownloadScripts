"""First method dowloading just one url"""
#quick and straightforward, then the urllib package
from urllib.request import urlretrieve
url = (
    "https://ttkb.meb.gov.tr/meb_iys_dosyalar/2024_01/24095558_2024_yks.pdf?downloadformat=pdf"
)
filename = "gdp_by_country.pdf"
urlretrieve(url, filename)

path, headers = urlretrieve(url, filename)
for name, value in headers.items():
    print(name, value)


"""Second method dowloading just one url"""
# import asyncio
# from directory_downloader import DDownloader

# async def main():
#     url ="https://ttkb.meb.gov.tr/meb_iys_dosyalar/2024_01/24095558_2024_yks.pdf"
#     downloader = DDownloader()
#     await downloader.crawl(url)  # fetch all the links from /directory/
#     await downloader.download_files(full_directory=r"C:/Users/fatma/SiberTurksat/deneme")  # download all files to current directory
    
# if __name__ == '__main__':
#     asyncio.run(main())


"""Third method dowloading just one url"""
#large files, then the requests library
# import requests
# url = "https://ttkb.meb.gov.tr/meb_iys_dosyalar/2024_01/24095558_2024_yks.pdf"
# query_parameters = {"downloadformat": "pdf"}
# response = requests.get(url, params=query_parameters)
# with open("yeni.pdf", "wb") as file:
#     file.write(response.content)


"""Fourth method downloading one url with small quantities"""
# import requests
# url = "https://databank.worldbank.org/data/download/WDI_CSV.zip"
# response = requests.get(url, stream=True)
# with open("WDI_CSV.zip", mode="wb") as file:
#      for chunk in response.iter_content(chunk_size=10 * 1024):
#          file.write(chunk)


"""Fifth method paralel url downloading(multithreading) """
# from concurrent.futures import ThreadPoolExecutor
# import requests

# def downloadFile(url):
#     response = requests.get(url)
#     if "content-disposition" in response.headers:
#         content_disposition = response.headers["content-disposition"]
#         filename = content_disposition.split("filename=")[1]
#     else:
#         filename = url.split("/")[-1]
#     with open(filename, mode="wb") as file:
#         file.write(response.content)
#     print(f"Downloaded file{filename}")

# template_url = ("https://api.worldbank.org/v2/en/indicator/"
#                 "{resource}?downloadformat=csv"
# )

# urls = [
#     # Total population by country
#     template_url.format(resource="SP.POP.TOTL"),

#     # GDP by country
#     template_url.format(resource="NY.GDP.MKTP.CD"),

#     # Population density by country
#     template_url.format(resource="EN.POP.DNST"),
# ]

# with ThreadPoolExecutor() as executor:
#     executor.map(downloadFile, urls)


"""Sixth method download multiple files concurrently"""
# import asyncio
# import aiohttp

# async def download_file(url):
#     async with aiohttp.ClientSession() as session:
#         async with session.get(url) as response:
#             if "content-disposition" in response.headers:
#                 header = response.headers["content-disposition"]
#                 filename = header.split("filename=")[1]
#             else:
#                 filename = url.split("/")[-1]
#             with open(filename, mode="wb") as file:
#                 while True:
#                     chunk = await response.content.read()
#                     if not chunk:
#                         break
#                     file.write(chunk)
#                 print(f"Downloaded file {filename}")

# template_url = (
#     "https://api.worldbank.org/v2/en/indicator/"
#     "{resource}?downloadformat=csv"
# )

# urls = [
#     # Total population by country
#     template_url.format(resource="SP.POP.TOTL"),

#     # GDP by country
#     template_url.format(resource="NY.GDP.MKTP.CD"),

#     # Population density by country
#     template_url.format(resource="EN.POP.DNST"),
# ]

# async def main():
#     tasks = [download_file(url) for url in urls]
#     await asyncio.gather(*tasks)

# asyncio.run(main())
