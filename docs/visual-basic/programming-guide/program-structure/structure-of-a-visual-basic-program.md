---
title: Estructura de un programa de Visual Basic | Documentos de Microsoft
ms.custom: 
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
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 64aab045538461d86946c870fa428bf8ad4ec15e
ms.lasthandoff: 03/13/2017

---
# <a name="structure-of-a-visual-basic-program"></a>Estructura de un programa de Visual Basic
Un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa se crea a partir de bloques de creación estándar. Un *solución* consta de uno o varios proyectos. Un *proyecto* a su vez puede contener uno o más ensamblados. Cada *ensamblado* se compila a partir de uno o varios archivos de origen. Un *archivo de código fuente* proporciona la definición e implementación de clases, estructuras, módulos e interfaces, que en última instancia contienen todo el código.  
  
 Para obtener más información acerca de estos bloques de creación de un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , consulte [soluciones y proyectos](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) y [ensamblados y la caché de ensamblados Global](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
## <a name="file-level-programming-elements"></a>Elementos de programación de nivel de archivo  
 Al iniciar un proyecto o archivo y abrir el editor de código, verá algún código ya en vigor y en el orden correcto. Cualquier código que escriba debe seguir la secuencia siguiente:  
  
1.  `Option`instrucciones  
  
2.  `Imports`instrucciones  
  
3.  `Namespace`instrucciones y los elementos de nivel de espacio de nombres  
  
 Si escribe instrucciones en un orden distinto, pueden producirse errores de compilación.  
  
 Un programa también puede contener instrucciones de compilación condicional. Pueden incluirse en el archivo de código fuente entre las instrucciones de la secuencia anterior.  
  
### <a name="option-statements"></a>Instrucciones de la opción  
 `Option`las instrucciones establecen reglas de base para el código subsiguiente, ayudando a evitar errores de sintaxis y la lógica. El [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) garantiza que todas las variables se declaran y ha escrito correctamente, lo que reduce el tiempo de depuración. El [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md) ayuda a minimizar la pérdida de datos y los errores de lógica que puede producirse al trabajar entre variables de diferentes tipos de datos. El [instrucción Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) especifica que se comparan las cadenas de manera entre sí, en función de sus `Binary` o `Text` valores.  
  
### <a name="imports-statements"></a>Instrucciones Imports  
 Puede incluir un [Imports (instrucción Namespace .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para importar nombres definidos fuera del proyecto. Un `Imports` instrucción permite que el código hacer referencia a clases y otros tipos definidos en el espacio de nombres importado sin tener que calificarlos. Puede utilizar tantas `Imports` instrucciones según corresponda. Para obtener más información, consulte [referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Instrucciones Namespace  
 Espacios de nombres le ayudarán a organiza y clasificar los elementos de programación para facilitar la agrupación y el acceso. Utiliza la [instrucción Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) para clasificar las instrucciones siguientes dentro de un espacio de nombres determinado. Para obtener más información, consulte [los espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Instrucciones de compilación condicional  
 Instrucciones de compilación condicional pueden aparecer prácticamente en cualquier parte del archivo de origen. Hacen que las partes del código se incluyan o excluyan en tiempo de compilación según ciertas condiciones. También puede utilizarlas para depurar la aplicación, porque el código condicional se ejecuta sólo en modo de depuración. Para obtener más información, consulte [compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Elementos de programación de nivel de Namespace  
 Clases, estructuras y módulos contienen todo el código del archivo de origen. Son *nivel de espacio de nombres* elementos, que pueden aparecer dentro de un espacio de nombres o en el nivel de archivos de origen. Contienen las declaraciones de todos los demás elementos de programación. Las interfaces, que definen firmas de elemento pero no proporcionan ninguna implementación, también aparecen en el nivel de módulo. Para obtener más información sobre los elementos de nivel de módulo, vea lo siguiente:  
  
-   [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Elementos de datos en el nivel de espacio de nombres son las enumeraciones y delegados.  
  
## <a name="module-level-programming-elements"></a>Elementos de programación de nivel de módulo  
 Los procedimientos, operadores, propiedades y eventos son los únicos elementos de programación que pueden contener código ejecutable (instrucciones que realizan acciones en tiempo de ejecución). Son el *nivel de módulo* elementos del programa. Para obtener más información sobre los elementos de nivel de procedimiento, vea lo siguiente:  
  
-   [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Elementos de datos en el nivel de módulo son las variables, constantes, enumeraciones y delegados.  
  
## <a name="procedure-level-programming-elements"></a>Elementos de programación de nivel de procedimiento  
 La mayoría del contenido de *nivel de procedimiento* elementos son instrucciones ejecutables, que constituyen el código de tiempo de ejecución del programa. Todo el código ejecutable debe estar en algún procedimiento (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Para obtener más información, consulte [instrucciones](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Elementos de datos en el nivel de procedimiento se limitan a las constantes y variables locales.  
  
## <a name="the-main-procedure"></a>El procedimiento principal  
 El `Main` procedimiento es el primer código que se ejecutará cuando se ha cargado su aplicación. `Main`actúa como punto de partida y control general de la aplicación. Hay cuatro variedades de `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 La variedad más común de este procedimiento es `Sub Main()`. Para obtener más información, consulte [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Limitaciones de Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
