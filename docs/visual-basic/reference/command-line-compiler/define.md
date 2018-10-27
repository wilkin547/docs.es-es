---
title: -Definir (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: 4cab6bc968275bc12af4365fd3da5e3b5ff417f2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195182"
---
# <a name="-define-visual-basic"></a>-Definir (Visual Basic)
Permite definir constantes condicionales para el compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`symbol`|Requerido. Símbolo que se va a definir.|  
|`value`|Opcional. Valor que se va a asignar a `symbol`. Si `value` es una cadena, se debe entrecomillar las secuencias de barra diagonal inversa/comillas (\\") en lugar de comillas. Si no se especifica ningún valor, se considera como verdadero.|  
  
## <a name="remarks"></a>Comentarios  
 El `-define` opción tiene un efecto similar al uso de un `#Const` directiva de preprocesador en el archivo de origen, excepto que las constantes definidas con `-define` son públicos y se aplican a todos los archivos del proyecto.  
  
 Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.  
  
 `-d` es la forma abreviada de `-define`.  
  
 Se pueden definir varios símbolos con `-define`; use una coma para separar las definiciones de símbolos.  
  
|Para definir/establecer en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el **constantes personalizadas** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se definen y usan dos constantes de compilador condicionales.  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
