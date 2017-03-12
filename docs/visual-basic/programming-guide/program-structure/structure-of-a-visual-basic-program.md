---
title: "Estructura de un programa de Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "compilación condicional, Visual Basic"
  - "procedimientos, estructura"
  - "estructura de programas, Visual Basic"
  - "código de Visual Basic, estructura de programas"
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Estructura de un programa de Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] se crea a partir de bloques de creación estándar.  Una *solución* consta de uno o varios proyectos.  Un *proyecto* a su vez puede contener uno o más ensamblados.  Cada *ensamblado* se compila a partir de uno o varios archivos de código fuente.  El *archivo de código fuente* proporciona la definición e implementación de clases, estructuras, módulos e interfaces, que en última instancia contienen todo el código.  
  
 Para obtener más información sobre estos bloques de creación de un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], vea [Soluciones y proyectos](/visual-studio/ide/solutions-and-projects-in-visual-studio) y [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Elementos de programación en el nivel de archivo  
 Al iniciar un proyecto o archivo y abrir el editor de código, verá que ya hay código en el lugar que le corresponde y en el orden correcto.  Cualquier código que escriba debe seguir la siguiente secuencia:  
  
1.  Instrucciones `Option`  
  
2.  Instrucciones `Imports`  
  
3.  Instrucciones `Namespace` y elementos del nivel de espacio de nombres  
  
 Si escribe instrucciones en un orden distinto, pueden producirse errores de compilación.  
  
 Un programa también puede contener instrucciones de compilación condicional.  Pueden incluirse en el archivo de código fuente entre las instrucciones de la secuencia anterior.  
  
### Instrucciones Option  
 Las instrucciones `Option` establecen reglas de base para el código subsiguiente, y de esta forma ayudan a prevenir errores de sintaxis y de lógica.  [Option Explicit \(Instrucción\)](../../../visual-basic/language-reference/statements/option-explicit-statement.md) garantiza que se declaran todas las variables y que se escriben correctamente, lo que reduce el tiempo de depuración.  La instrucción [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md) ayuda a reducir errores de lógica y pérdidas de datos que puedan producirse al trabajar entre variables de diferentes tipos de datos.  [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md) especifica la manera en que se comparan las cadenas entre sí, según sus valores `Binary` o `Text`.  
  
### Instrucciones Imports  
 Puede incluir [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para importar nombres definidos fuera del proyecto.  Las instrucciones `Imports` permiten que el código haga referencia a clases y otros tipos definidos en el espacio de nombres importado sin tener que calificarlos.  Puede utilizar tantas instrucciones `Imports` como sea necesario.  Para obtener más información, vea [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### Instrucciones Namespace  
 Los espacios de nombres ayudan a organizar y clasificar los elementos de programación para facilitar la agrupación y el acceso.  Utiliza [Namespace \(Instrucción\)](../../../visual-basic/language-reference/statements/namespace-statement.md) para clasificar las instrucciones siguientes dentro de un espacio de nombres determinado.  Para obtener más información, vea [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### Instrucciones de compilación condicional  
 Las instrucciones de compilación condicional pueden aparecer prácticamente en cualquier parte del archivo de código fuente.  Determinan que partes del código se incluyan o excluyan en tiempo de compilación en función de ciertas condiciones.  También puede utilizarlas para depurar la aplicación, ya que el código condicional se ejecuta únicamente en modo de depuración.  Para obtener más información, vea [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## Elementos de programación en el nivel de espacio de nombres  
 Las clases, estructuras y módulos contienen todo el código del archivo de código fuente.  Son elementos del *nivel de espacio de nombres*, que pueden aparecer dentro de un espacio de nombres o en el nivel del archivo de código fuente.  Contienen las declaraciones de todos los demás elementos de programación.  Las interfaces, que definen firmas de elemento pero no proporcionan ninguna implementación, también aparecen en el nivel de módulo.  Para obtener más información sobre los elementos del nivel de módulo, vea los siguientes temas:  
  
-   [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Los elementos de datos en el nivel de espacio de nombres son las enumeraciones y los delegados.  
  
## Elementos de programación en el nivel de módulo  
 Los procedimientos, operadores, propiedades y eventos son los únicos elementos de programación que pueden contener código ejecutable \(instrucciones que realizan acciones en tiempo de ejecución\).  Son elementos del *nivel de módulo* del programa.  Para obtener más información sobre los elementos del nivel de procedimiento, vea los siguientes temas:  
  
-   [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Los elementos de datos en el nivel de módulo son las variables, las constantes, las enumeraciones y los delegados.  
  
## Elementos de programación en el nivel de procedimiento  
 La mayoría del contenido de los elementos del *nivel de procedimiento* son instrucciones ejecutables, que constituyen el código en tiempo de ejecución del programa.  Todo el código ejecutable debe estar incluido en algún procedimiento \(`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`\).  Para obtener más información, vea [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Los elementos de datos en el nivel de procedimiento se limitan a las constantes y las variables locales.  
  
## Procedimiento Main  
 El procedimiento `Main` es el primer código que se ejecuta cuando se ha cargado su aplicación.  `Main` actúa como punto de partida y control general de la aplicación.  Hay cuatro variedades de `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 La variedad más común de este procedimiento es `Sub Main()`.  Para obtener más información, vea [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## Vea también  
 [Versión de Visual Basic del programa Hola a todos](http://msdn.microsoft.com/es-es/9d030b60-e148-4366-a462-69532f02294c)   
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Limitaciones de Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)