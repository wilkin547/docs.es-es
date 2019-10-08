---
title: -linkresource ((Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: dee5384696d543442f3280b9fdb535a7d9b6f863
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005491"
---
# <a name="-linkresource-visual-basic"></a>-linkresource ((Visual Basic)
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
 Obligatorio. Archivo de recursos que se va a vincular al ensamblado. Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").  
  
 `identifier`  
 Opcional. Nombre lógico del recurso. Nombre que se usa para cargar el recurso. El valor predeterminado es el nombre del archivo. Opcionalmente, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `-linkres:filename.res,myname.res,public`. De forma predeterminada, `filename` es público en el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 La opción `-linkresource` no incrusta el archivo de recursos en el archivo de salida; Use la opción `-resource` para hacerlo.  
  
 La opción `-linkresource` requiere una de las opciones `-target` distintas de `-target:module`.  
  
 Si `filename` es un archivo de recursos .NET Framework creado, por ejemplo, mediante [Resgen. exe (generador de archivos de recursos)](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede tener acceso al mismo con miembros del espacio de nombres <xref:System.Resources>. (Para obtener más información, vea <xref:System.Resources.ResourceManager>). Para tener acceso a todos los demás recursos en tiempo de ejecución, use los métodos que comienzan por `GetManifestResource` en la clase <xref:System.Reflection.Assembly>.  
  
 El nombre de archivo puede tener cualquier formato de archivo. Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.  
  
 La forma abreviada de `-linkresource` es `-linkres`.  
  
> [!NOTE]
> La opción `-linkresource` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `in.vb` y los vínculos al archivo de recursos `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
