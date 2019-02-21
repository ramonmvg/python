import speedtest
import telegram
import mysql.connector as mariadb

#mariadb_connection = mariadb.connect(user='xxxxxxx', password='XXXXX',host='localhost', port=XXX, database='xxxxx')
#cursor = mariadb_connection.cursor()
bot = telegram.Bot(token='XXXXX')

s = speedtest.Speedtest()
s.get_best_server()
s.download()
s.upload()
s.results.share()

results_dict = s.results.dict()
ping = results_dict['ping']
url = results_dict['share']
isp = results_dict['client']['isp']
pubip = results_dict['client']['ip']
server = results_dict['server']['name']
down=results_dict['download']/1048576
uplo=results_dict['upload']/1048576
download=str("%.2f" % down)
upload=str("%.2f" % uplo)

#Imprime el resultado con todos los datos
# print results_dict
print (pubip, isp, server)

if down < 500 or uplo < 50:
    print ("Hay un problema en la linea")
    print (download, upload, ping, url)
    #cursor.execute("INSERT INTO tb_homelinestat (pubip, operador, servidorpru, lat, download, upload, url) VALUES (%s,%s,%s,%s,%s,%s,%s)",(pubip, isp, server, ping, download, upload, url))
    #mariadb_connection.commit()
    #mariadb_connection.close()
    bot.send_message(chat_id="xxxxxxx", text=url+' Hay un problema en la linea')
else:
    print ("Velocidad correcta")
    print (download, upload, ping, url)
    #cursor.execute("INSERT INTO tb_homelinestat (pubip, operador, servidorpru, lat, download, upload, url) VALUES (%s,%s,%s,%s,%s,%s,%s)",(pubip, isp, server, ping, download, upload, url))
    #mariadb_connection.commit()
    #mariadb_connection.close()

print ("Prueba finalizada correctamente")
