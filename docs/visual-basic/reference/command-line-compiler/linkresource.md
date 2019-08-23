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
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924857"
---
# <a name="-linkresource-visual-basic"></a>-linkresource ((Visual Basic)
Crea un vínculo a un recurso administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 Necesario. Archivo de recursos que se va a vincular al ensamblado. Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").  
  
 `identifier`  
 Opcional. Nombre lógico del recurso. Nombre que se usa para cargar el recurso. El valor predeterminado es el nombre del archivo. Opcionalmente, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo `-linkres:filename.res,myname.res,public`:. De forma predeterminada `filename` , es público en el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 La `-linkresource` opción no incrusta el archivo de recursos en el archivo de salida; Use `-resource` la opción para hacerlo.  
  
 La `-linkresource` opción requiere una de las `-target` opciones que no `-target:module`sean.  
  
 Si `filename` es un .NET Framework archivo de recursos creado, por ejemplo, mediante [Resgen. exe (generador de archivos de recursos)](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede tener acceso al mismo <xref:System.Resources> con miembros del espacio de nombres. (Para obtener más información, vea <xref:System.Resources.ResourceManager>). Para tener acceso a todos los demás recursos en tiempo de ejecución, use los `GetManifestResource` métodos que <xref:System.Reflection.Assembly> comienzan por en la clase.  
  
 El nombre de archivo puede tener cualquier formato de archivo. Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.  
  
 La forma abreviada de `-linkresource` es `-linkres`.  
  
> [!NOTE]
> La `-linkresource` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `in.vb` y vincula al archivo `rf.resource`de recursos.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
