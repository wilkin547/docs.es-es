---
title: /linkresource (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fafde6563340189108a879b82e7e880aca690b39
ms.lasthandoff: 03/13/2017

---
# <a name="linkresource-visual-basic"></a>/linkresource (Visual Basic)
Crea un vínculo a un recurso administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 Obligatorio. Archivo de recursos que se va a vincular al ensamblado. Si el nombre de archivo contiene un espacio, encierre el nombre entre comillas ("").  
  
 `identifier`  
 Opcional. El nombre lógico del recurso. El nombre que se utiliza para cargar el recurso. El valor predeterminado es el nombre del archivo. Opcionalmente, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `/linkres:filename.res,myname.res,public`. De forma predeterminada, `filename` es público en el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 El `/linkresource` opción no incrusta el archivo de recursos en el archivo de salida; utilice la `/resource` opción para hacerlo.  
  
 El `/linkresource` opción requiere uno de los `/target` opciones distinto de `/target:module`.  
  
 Si `filename` es una [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] archivo de recursos creado, por ejemplo, con el [Resgen.exe (generador de archivos de recursos)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) o en el entorno de desarrollo, se puede tener acceso a los miembros de la <xref:System.Resources>espacio de nombres.</xref:System.Resources> (Para obtener más información, consulte <xref:System.Resources.ResourceManager>.)</xref:System.Resources.ResourceManager> Para obtener acceso a todos los demás recursos en tiempo de ejecución, utilice los métodos que comienzan por `GetManifestResource` en la <xref:System.Reflection.Assembly>clase.</xref:System.Reflection.Assembly>  
  
 El nombre de archivo puede tener cualquier formato de archivo. Por ejemplo, desea realizar una DLL nativa forme parte del ensamblado, por lo que se puede instalar en la caché global de ensamblados y accesible desde código administrado del ensamblado.  
  
 La forma abreviada de `/linkresource` es `/linkres`.  
  
> [!NOTE]
>  El `/linkresource` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y vínculos al archivo de recursos `Rf.resource`.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
