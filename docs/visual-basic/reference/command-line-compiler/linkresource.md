---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 97e0ccd46f413cc05b659731436bb141ee178419
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034563"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Crea un vínculo a un recurso administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 Requerido. El archivo de recursos para vincular al ensamblado. Si el nombre de archivo contiene un espacio, escriba el nombre entre comillas ("").  
  
 `identifier`  
 Opcional. El nombre lógico del recurso. El nombre que se usa para cargar el recurso. El valor predeterminado es el nombre del archivo. Si lo desea, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `-linkres:filename.res,myname.res,public`. De forma predeterminada, `filename` es público en el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 El `-linkresource` opción no incrusta el archivo de recursos en el archivo de salida; utilice el `-resource` opción para hacer esto.  
  
 El `-linkresource` opción requiere uno de los `-target` opciones distintas de `-target:module`.  
  
 Si `filename` es un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos creado, por ejemplo, con el [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, puede obtenerse con los miembros de la <xref:System.Resources> espacio de nombres. (Para obtener más información, vea <xref:System.Resources.ResourceManager>). Para obtener acceso a todos los demás recursos en tiempo de ejecución, utilice los métodos que comienzan por `GetManifestResource` en el <xref:System.Reflection.Assembly> clase.  
  
 El nombre de archivo puede ser cualquier formato de archivo. Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.  
  
 La forma abreviada de `-linkresource` es `-linkres`.  
  
> [!NOTE]
>  El `-linkresource` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `in.vb` y vínculos al archivo de recursos `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
- [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)  
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
