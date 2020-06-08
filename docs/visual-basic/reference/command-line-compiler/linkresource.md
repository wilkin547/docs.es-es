---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 43ebb61efa26ed11af573e2c4e73a6fd71ac0902
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403205"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Crea un vínculo a un recurso administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

o  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 Obligatorio. El archivo de recursos que se va a vincular al ensamblado. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").  
  
 `identifier`  
 Opcional. El nombre lógico del recurso. El nombre que se usa para cargar el recurso. El valor predeterminado es el nombre del archivo. Opcionalmente, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `-linkres:filename.res,myname.res,public`. De forma predeterminada, `filename` es público en el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 La opción `-linkresource` no inserta el archivo de recursos en el archivo de salida; para hacerlo, use la opción `-resource`.  
  
 La opción `-linkresource` requiere una de las opciones de `-target` que no sea `-target:module`.  
  
 Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, por Resgen.exe ([Generador de archivos de recursos](../../../framework/tools/resgen-exe-resource-file-generator.md)) o en el entorno de desarrollo, se puede acceder al mismo con miembros del espacio de nombres <xref:System.Resources>. (Para obtener más información, vea <xref:System.Resources.ResourceManager>). Para acceder a todos los demás recursos en tiempo de ejecución, use los métodos que empiezan por `GetManifestResource` de la clase <xref:System.Reflection.Assembly>.  
  
 El nombre de archivo puede tener cualquier formato de archivo. Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.  
  
 La forma abreviada de `-linkresource` es `-linkres`.  
  
> [!NOTE]
> La opción `-linkresource` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se compila `in.vb` y se vincula al archivo de recursos `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [-resource (Visual Basic)](resource.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
