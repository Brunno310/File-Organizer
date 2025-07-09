import os
import shutil

pasta = 'arquivos'

tipos = {
    'imagens': ['.jpg', '.jpeg', '.png', '.gif'],
    'documentos': ['.pdf', '.docx', '.txt'],
    'planilhas': ['.xlsx', '.csv'],
    'videos': ['.mp4', '.mov', '.avi'],
    'compactados': ['.zip', '.rar'],
    'outros': []
}

for tipo in tipos:
    caminho = os.path.join(pasta, tipo)
    os.makedirs(caminho, exist_ok=True)

for arquivo in os.listdir(pasta):
    caminho_arquivo = os.path.join(pasta, arquivo)

    if os.path.isfile(caminho_arquivo):
        _, extensao = os.path.splitext(arquivo)
        movido = False

        for tipo, extensoes in tipos.items():
            if extensao.lower() in extensoes:
                destino = os.path.join(pasta, tipo, arquivo)
                shutil.move(caminho_arquivo, destino)
                movido = True
                break

        if not movido:
            destino = os.path.join(pasta, 'outros', arquivo)
            shutil.move(caminho_arquivo, destino)
