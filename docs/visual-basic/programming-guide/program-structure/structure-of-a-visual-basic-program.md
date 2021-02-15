---
description: 'Más información acerca de: estructura de un programa de Visual Basic'
title: Estructura de un programa de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: e5941b1cbdfdc460e3e860a5449e8ccae0673612
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468205"
---
# <a name="structure-of-a-visual-basic-program"></a>Estructura de un programa de Visual Basic

Un programa de Visual Basic se crea a partir de los bloques de creación estándar. Una *solución* consta de uno o varios proyectos. Un *proyecto* A su vez puede contener uno o más ensamblados. Cada *ensamblado* se compila a partir de uno o más archivos de código fuente. Un *archivo de código fuente* proporciona la definición y la implementación de clases, estructuras, módulos e interfaces, que en última instancia contienen todo el código.  
  
 Para obtener más información sobre estos bloques de creación de un programa de Visual Basic, vea [soluciones y proyectos](/visualstudio/ide/solutions-and-projects-in-visual-studio) y [ensamblados en .net](../../../standard/assembly/index.md).  
  
## <a name="file-level-programming-elements"></a>File-Level elementos de programación  

 Al iniciar un proyecto o un archivo y abrir el editor de código, verá que ya hay código en su lugar y en el orden correcto. Cualquier código que escriba debe seguir la siguiente secuencia:  
  
1. `Option` afirma  
  
2. `Imports` afirma  
  
3. `Namespace` instrucciones y elementos de nivel de espacio de nombres  
  
 Si escribe instrucciones en un orden diferente, pueden producirse errores de compilación.  
  
 Un programa también puede contener instrucciones de compilación condicional. Puede entremezclarlos en el archivo de código fuente entre las instrucciones de la secuencia anterior.  
  
### <a name="option-statements"></a>Instrucciones Option  

 `Option` las instrucciones establecen reglas de la base para el código subsiguiente, lo que ayuda a evitar errores de sintaxis y lógica. La [instrucción Option Explicit](../../language-reference/statements/option-explicit-statement.md) garantiza que todas las variables se declaran y se escriben correctamente, lo que reduce el tiempo de depuración. La [instrucción Option Strict](../../language-reference/statements/option-strict-statement.md) ayuda a minimizar los errores lógicos y la pérdida de datos que se pueden producir al trabajar entre variables de tipos de datos diferentes. La [instrucción Option Compare](../../language-reference/statements/option-compare-statement.md) especifica el modo en que se comparan las cadenas entre sí, en función de sus `Binary` `Text` valores o.  
  
### <a name="imports-statements"></a>Instrucciones Imports  

 Puede incluir una [instrucción Imports (espacio de nombres y tipo .net)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) para importar nombres definidos fuera del proyecto. Una `Imports` instrucción permite que el código haga referencia a clases y otros tipos definidos en el espacio de nombres importado, sin tener que calificarlos. Puede utilizar tantas `Imports` instrucciones como sea necesario. Para obtener más información, vea [referencias y la instrucción Imports](references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Instrucciones de espacio de nombres  

 Los espacios de nombres ayudan a organizar y clasificar los elementos de programación para facilitar la agrupación y el acceso. Use la [instrucción namespace](../../language-reference/statements/namespace-statement.md) para clasificar las siguientes instrucciones dentro de un espacio de nombres determinado. Para más información, consulte [Espacios de nombres en Visual Basic](namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Instrucciones de compilación condicional  

 Las instrucciones de compilación condicional pueden aparecer prácticamente en cualquier parte del archivo de código fuente. Hacen que las partes del código se incluyan o excluyan en tiempo de compilación en función de ciertas condiciones. También puede usarlos para depurar la aplicación, ya que el código condicional solo se ejecuta en modo de depuración. Para obtener más información, vea [compilación condicional](conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Namespace-Level elementos de programación  

 Las clases, las estructuras y los módulos contienen todo el código del archivo de código fuente. Son elementos *de nivel de espacio de nombres* , que pueden aparecer dentro de un espacio de nombres o en el nivel de archivo de origen. Contienen las declaraciones de todos los demás elementos de programación. Las interfaces, que definen las signaturas de los elementos, pero no proporcionan ninguna implementación, también aparecen en el nivel de módulo. Para obtener más información sobre los elementos de nivel de módulo, vea lo siguiente:  
  
- [Instrucción Class](../../language-reference/statements/class-statement.md)  
  
- [Structure (Instrucción)](../../language-reference/statements/structure-statement.md)  
  
- [Module (Instrucción)](../../language-reference/statements/module-statement.md)  
  
- [Instrucción Interface](../../language-reference/statements/interface-statement.md)  
  
 Los elementos de datos en el nivel de espacio de nombres son enumeraciones y delegados.  
  
## <a name="module-level-programming-elements"></a>Module-Level elementos de programación  

 Los procedimientos, operadores, propiedades y eventos son los únicos elementos de programación que pueden contener código ejecutable (instrucciones que realizan acciones en tiempo de ejecución). Son los elementos de *nivel de módulo* del programa. Para obtener más información sobre los elementos de nivel de procedimiento, vea lo siguiente:  
  
- [Instrucción Function](../../language-reference/statements/function-statement.md)  
  
- [Instrucción Sub](../../language-reference/statements/sub-statement.md)  
  
- [Declare Statement](../../language-reference/statements/declare-statement.md)  
  
- [Operator Statement](../../language-reference/statements/operator-statement.md)  
  
- [Property Statement](../../language-reference/statements/property-statement.md)  
  
- [Event (Instrucción)](../../language-reference/statements/event-statement.md)  
  
 Los elementos de datos en el nivel de módulo son variables, constantes, enumeraciones y delegados.  
  
## <a name="procedure-level-programming-elements"></a>Procedure-Level elementos de programación  

 La mayor parte del contenido de los elementos de *nivel de procedimiento* son instrucciones ejecutables, que constituyen el código en tiempo de ejecución del programa. Todo el código ejecutable debe estar en algún procedimiento ( `Function` , `Sub` , `Operator` , `Get` , `Set` , `AddHandler` , `RemoveHandler` , `RaiseEvent` ). Para más información, vea [Statements](../language-features/statements.md) (Instrucciones).  
  
 Los elementos de datos en el nivel de procedimiento se limitan a las variables locales y a las constantes.  
  
## <a name="the-main-procedure"></a>El procedimiento Main  

 El `Main` procedimiento es el primer código que se ejecuta cuando se carga la aplicación. `Main` sirve como punto de partida y control general de la aplicación. Hay cuatro variedades de `Main` :  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 La variedad más común de este procedimiento es `Sub Main()` . Para obtener más información, vea el [procedimiento Main en Visual Basic](main-procedure.md).  
  
## <a name="see-also"></a>Consulte también

- [Procedimiento Main en Visual Basic](main-procedure.md)
- [Convenciones de nomenclatura de Visual Basic](naming-conventions.md)
- [Limitaciones de Visual Basic](limitations.md)
