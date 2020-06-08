---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0d1b03d9ab98f28a0112198f1ecc1e928d6d4a7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408717"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
Permite definir constantes condicionales para el compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

o

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`symbol`|Obligatorio. Símbolo que se va a definir.|  
|`value`|Opcional. Valor que se va a asignar a `symbol`. Si `value` es una cadena, se debe incluir entre secuencias de barra diagonal inversa/ y comillas (\\") en lugar de entre comillas. Si no se especifica ningún valor, se considera como verdadero.|  
  
## <a name="remarks"></a>Comentarios  
 La opción `-define` tiene un efecto similar a usar una directiva de preprocesador `#Const` en el archivo de origen, salvo por el hecho de que las constantes definidas con `-define` son públicas y se aplican a todos los archivos del proyecto.  
  
 Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.  
  
 `-d` es la forma abreviada de `-define`.  
  
 Se pueden definir varios símbolos con `-define`; use una coma para separar las definiciones de símbolos.  
  
|Para establecer -define en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Cambie el valor del cuadro **Constantes personalizadas**.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se definen y usan dos constantes de compilador condicionales.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [#If...Then...#Else (directivas)](../../language-reference/directives/if-then-else-directives.md)
- [#Const (directiva)](../../language-reference/directives/const-directive.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
