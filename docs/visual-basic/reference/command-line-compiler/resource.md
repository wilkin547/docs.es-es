---
title: -resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 2d7da572ecc8d7d20917eaa244eefbcd7abe61f0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589511"
---
# <a name="-resource-visual-basic"></a>-resource (Visual Basic)
Inserta un recurso administrado en un ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|Obligatorio. El nombre del archivo de recursos para insertar en el archivo de salida. De forma predeterminada, `filename` es público en el ensamblado. Ponga el nombre de archivo entre comillas ("") si contiene un espacio.|  
|`identifier`|Opcional. El nombre lógico del recurso; el nombre utilizado para cargarlo. El valor predeterminado es el nombre del archivo. Si lo desea, puede especificar si el recurso es público o privado en el manifiesto del ensamblado, al igual que con los siguientes: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Comentarios  
 Use `-linkresource` para vincular un recurso a un ensamblado sin incluir el archivo de recursos en el archivo de salida.  
  
 Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, con el [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, puede obtenerse con los miembros de la <xref:System.Resources> espacio de nombres (consulte <xref:System.Resources.ResourceManager> para obtener más información). Para obtener acceso a todos los demás recursos en tiempo de ejecución, utilice uno de los métodos siguientes: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 La forma abreviada de `-resource` es `-res`.  
  
 Para obtener información sobre cómo establecer `-resource` en el IDE de Visual Studio, consulte [administrar aplicación de recursos (. NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y archivo de recursos adjunta `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
