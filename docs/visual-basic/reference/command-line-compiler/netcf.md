---
title: /netcf | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
dev_langs:
- VB
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d8e2328eb5434ea0e73238709c429975ae29e6d0
ms.lasthandoff: 03/13/2017

---
# <a name="netcf"></a>/netcf
Establece el compilador con destino en [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/netcf  
```  
  
## <a name="remarks"></a>Comentarios  
 El `/netcf` opción causas la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador destino el [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] en lugar de toda la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Funcionalidad del lenguaje que sólo está presente en el completo [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] está deshabilitado.  
  
 El `/netcf` opción está diseñada para usarse con [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Las características de lenguaje deshabilitadas por `/netcf` son las mismas características de lenguaje no está presentes en los archivos de destino con `/sdkpath`.  
  
> [!NOTE]
>  El `/netcf` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos. El `/netcf` opción se establece cuando un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] se carga un proyecto de dispositivo.  
  
 El `/netcf` opción cambia las características de lenguaje siguientes:  
  
-   El [End \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) (palabra clave), que finaliza la ejecución de un programa, está deshabilitada. El programa siguiente se compila y se ejecuta sin `/netcf` , pero se produce un error en tiempo de compilación con `/netcf`.  
  
     [!code-vb[VbVbalrCompiler&#34;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   Está deshabilitado el enlace más tarde en todos los formularios. Se generan errores en tiempo de compilación cuando se encuentran escenarios de enlace reconocidos. El programa siguiente se compila y se ejecuta sin `/netcf` , pero se produce un error en tiempo de compilación con `/netcf`.  
  
     [!code-vb[VbVbalrCompiler&#35;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   El [automática](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), y [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificadores están deshabilitados. La sintaxis de la [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) también se modifica la instrucción en `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. El código siguiente muestra el efecto de `/netcf` en una compilación.  
  
     [!code-vb[VbVbalrCompiler&#36;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Uso de palabras clave de Visual Basic 6.0 que se quitaron de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] genera un error diferente cuando `/netcf` se utiliza. Esto afecta a los mensajes de error para las palabras clave siguientes:  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], utilizando las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll que se encuentra en el directorio de instalación predeterminado de la [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] en la unidad C:. Normalmente, utilizaría la versión más reciente de la [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
