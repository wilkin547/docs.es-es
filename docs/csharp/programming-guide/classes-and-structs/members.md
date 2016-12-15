---
title: "Miembros (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, miembros de tipo"
  - "tipos [C#], tipos anidados"
ms.assetid: 4a30a4ab-d690-4936-9124-92ce9448665a
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Miembros (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las clases y structs tienen miembros que representan sus datos y comportamiento.  Los miembros de una clase incluyen todos los miembros declarados en la clase, junto con todos los miembros \(excepto constructores y destructores\) declarados en todas las clases de su jerarquía de herencia.  Los miembros privados de clases base se heredan en las clases derivadas, pero estas no pueden tener acceso a ellos.  
  
 En la tabla siguiente se enumeran los tipos de miembros que puede contener una clase o struct:  
  
|Miembro|Descripción|  
|-------------|-----------------|  
|[Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)|Los campos son variables declaradas en el ámbito de clase.  Un campo puede ser un tipo numérico integrado o una instancia de otra clase.  Por ejemplo, una clase de calendario puede tener un campo con la fecha actual.|  
|[Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)|Las constantes son campos o propiedades cuyo valor se establece en tiempo de compilación y no se puede cambiar.|  
|[Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)|Las propiedades son métodos de una clase a los que se obtiene acceso como si fueran campos de esa clase.  Una propiedad puede proporcionar protección a un campo de clase con el fin de evitar que se cambie sin el conocimiento del objeto.|  
|[Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)|Los métodos definen las acciones que una clase puede realizar.  Los métodos pueden aceptar parámetros que proporcionan datos de entrada y devolver datos de salida a través de parámetros.  Los métodos también pueden devolver un valor directamente, sin usar ningún parámetro.|  
|[Eventos](../../../csharp/programming-guide/events/index.md)|Los eventos proporcionan a otros objetos notificaciones sobre lo que ocurre, como clics en botones o la realización correcta de un método.  Los eventos se definen y desencadenan mediante delegados.|  
|[Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|Los operadores sobrecargados se consideran miembros de clase.  Si se sobrecarga un operador, se define como método estático público en una clase.  Los operadores predefinidos \(`+`, `*`, `<`, etc.\) no se consideran miembros.  Para obtener más información, vea [Operadores sobrecargables](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).|  
|[Indizadores](../../../csharp/programming-guide/indexers/index.md)|Los indizadores permiten indizar un objeto de manera similar a como se hace con las matrices.|  
|[Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)|Los constructores son métodos a los que se llama cuando el objeto se crea por primera vez.  Se usan a menudo para inicializar los datos de un objeto.|  
|[Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)|En C\#, los destructores se usan en raras ocasiones.  Son métodos a los que llama el motor de ejecución del runtime cuando el objeto está a punto de quitarse de la memoria.  Generalmente se utilizan para asegurarse de que los recursos que se deben liberar se controlan apropiadamente.|  
|[Tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md)|Los tipos anidados son tipos declarados dentro de otro tipo.  Los tipos anidados se usan a menudo para describir objetos utilizados únicamente por los tipos que los contienen.|  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md)   
 [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [Operadores sobrecargables](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)