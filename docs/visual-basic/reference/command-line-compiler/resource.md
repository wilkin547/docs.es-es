---
title: -Resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 5bedc346381f6de293933dce14a8c5c3044b246f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005194"
---
# <a name="-resource-visual-basic"></a>-Resource (Visual Basic)
Inserta un recurso administrado en un ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

o  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|Obligatorio. Nombre del archivo de recursos que se va a insertar en el archivo de salida. De forma predeterminada, `filename` es público en el ensamblado. Escriba el nombre de archivo entre comillas ("") si contiene un espacio.|  
|`identifier`|Opcional. Nombre lógico del recurso; nombre usado para cargarlo. El valor predeterminado es el nombre del archivo. Opcionalmente, puede especificar si el recurso es público o privado en el manifiesto del ensamblado, como en el siguiente: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Comentarios  
 Use `-linkresource` para vincular un recurso a un ensamblado sin colocar el archivo de recursos en el archivo de salida.  
  
 Si `filename` es un archivo de recursos .NET Framework creado, por ejemplo, mediante [Resgen. exe (generador de archivos de recursos)](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede tener acceso al mismo con miembros del espacio de nombres <xref:System.Resources> (vea <xref:System.Resources.ResourceManager> para obtener más información). Para tener acceso a todos los demás recursos en tiempo de ejecución, use uno de los métodos siguientes: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 La forma abreviada de `-resource` es `-res`.  
  
 Para obtener información sobre cómo establecer `-resource` en el IDE de Visual Studio, vea [administrar recursos de la aplicación (.net)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y adjunta el archivo de recursos `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource ((Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
