---
title: Compilación condicional en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 496df36242c6b43e7e3ec94ce675d11177e8b466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653022"
---
# <a name="conditional-compilation-in-visual-basic"></a>Compilación condicional en Visual Basic
En *compilación condicional*, bloques concretos de código en un programa se compilan de forma selectiva mientras que otros se omiten.  
  
 Por ejemplo, puede que desee escribir instrucciones de depuración que comparen la velocidad de enfoques diferentes en la misma tarea de programación, o bien puede adaptar una aplicación para varios idiomas. Instrucciones de compilación condicional están diseñadas para ejecutarse durante el tiempo de compilación, no en tiempo de ejecución.  
  
 Denota bloques de código que se compilarán con la `#If...Then...#Else` directiva. Por ejemplo, para crear francés y alemán versiones de la misma aplicación desde el mismo código fuente, incruste segmentos de código específico de plataforma en `#If...Then` instrucciones mediante las constantes predefinidas `FrenchVersion` y `GermanVersion`. En el ejemplo siguiente se muestra cómo:  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 Si establece el valor de la `FrenchVersion` constante de compilación condicional para `True` en tiempo de compilación, se compila el código condicional de la versión en francés. Si establece el valor de la `GermanVersion` constante a `True`, el compilador usa la versión en alemán. Si no está establecida `True`, el código en los últimos `Else` bloquear ejecuciones.  
  
> [!NOTE]
>  Autocompletar serán no funcionará al editar código y utiliza directivas de compilación condicional si el código no forma parte de la rama actual.  
  
## <a name="declaring-conditional-compilation-constants"></a>Declarar constantes de compilación condicional  
 Puede establecer las constantes de compilación condicional en una de estas tres maneras:  
  
-   En el **Diseñador de proyectos**  
  
-   En la línea de comandos cuando se usa el compilador de línea de comandos  
  
-   En el código  
  
 Constantes de compilación condicional tienen un ámbito especial y no se pueden tener acceso desde el código estándar. El ámbito de una constante de compilación condicional es dependiente de la manera en que se establece. En la tabla siguiente muestra el ámbito de las constantes declaradas con cada uno de los tres métodos mencionados anteriormente.  
  
|¿Cómo se establece (constante)|Ámbito de constante|  
|---|---|  
|**Diseñador de proyectos**|Público para todos los archivos en el proyecto|  
|Línea de comandos|Público para todos los archivos que se pasó al compilador de línea de comandos|  
|`#Const` instrucción de código|Privado para el archivo en el que se declara|  
  
|Para definir constantes en el Diseñador de proyectos|  
|---|  
|-Antes de crear el archivo ejecutable, defina las constantes en el **Diseñador de proyectos** siguiendo los pasos indicados en [administrar proyecto y propiedades de la solución](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Para definir constantes en la línea de comandos|  
|---|  
|-Use el **/d** conmutador para especificar constantes de compilación condicional, como en el ejemplo siguiente:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     No se requiere ningún espacio entre el **/d** conmutador y la primera constante. Para obtener más información, consulte [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Las declaraciones de la línea de comandos reemplazan a las especificadas en el **Diseñador de proyectos**, pero no las borran. Argumentos que se establecen **Diseñador de proyectos** siguen en vigor para las compilaciones subsiguientes.<br />     Al escribir constantes en el propio código, no hay ninguna regla estricta en cuanto a su ubicación, puesto que su ámbito es el módulo completo en el que se declaran.|  
  
|Para definir constantes en el código|  
|---|  
|-Coloque las constantes en el bloque de declaración del módulo en el que se utilizan. Esto ayuda a mantener el código organizada y fáciles de leer.|  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|---|---|  
|[Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Proporciona sugerencias para hacer que su código sea fácil de leer y mantener.|  
  
## <a name="reference"></a>Referencia  
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
