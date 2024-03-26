## Como configurar um projeto unreal pra usar git e git-lfs no Windows
### Ferramentas necessarias:
- [Github desktop](https://desktop.github.com)
- [Git](https://git-scm.com)
- [Git Large File Storage](https://git-lfs.com/)

### Passos
1) Na unreal, no canto inferior direito, clicar em "Connect to revision control". Isso fara abrir uma janela com novas opções.

![image](https://github.com/henrique-dev/unreal-tips/assets/23532516/d4efbc37-77a2-430a-8387-9d8f7f278f75)

2) Aqui deve ser marcado "Add a .gitignore file", "Add a basic README.md file" e "Add a .gitaatributes file to enable Git LFS". Deve deixar desmarcado a opção "Make the initial commit". Depois é só clicar em "Initialize project with git".

![image](https://github.com/henrique-dev/unreal-tips/assets/23532516/d0f4b888-0a49-431c-8881-a1243f1be273)

3) Agora é só clicar em "Accept Settings".

![image](https://github.com/henrique-dev/unreal-tips/assets/23532516/e21555a4-9bec-4057-97a9-f7ab42debafe)

4) O proximo passo é ir no github desktop e adicionar o repositorio existente a partir do computador.

![image](https://github.com/henrique-dev/unreal-tips/assets/23532516/979ed0be-db1c-4748-b731-7ae7763555e7)

5) Após adicionar o repositorio, aparecera uma jenala sobre o Git LFS, então é só confirmar clicando em "Initialize Git LFS".

![image](https://github.com/henrique-dev/unreal-tips/assets/23532516/08d26c5b-5357-45cf-a9fa-8cea73c9a4ed)

6) Devemos editar o arquivo em nosso projeto chamado `.gitattributes`, e incluir o seguinte trecho: `*.uasset filter=lfs diff=lfs merge=lfs -text`. O arquivo ficara assim:
> .gitattributes
```
Content/** filter=lfs diff=lfs merge=lfs -text
*.uasset filter=lfs diff=lfs merge=lfs -text
```

![image](https://github.com/henrique-dev/unreal-tips/assets/23532516/479295c3-0fd2-4d95-bd63-891217aa201d)

7) Agora devemos publicar para o repositorio remoto primeiro e somente o arquivo `.gitattributes`.

![image](https://github.com/henrique-dev/unreal-tips/assets/23532516/8e7de477-f929-4f2b-92c6-1f56829ea16e)

8) E pra finalizar, podemos adicionar todos os outros arquivos do projeto, e publicar no repositorio remoto.
