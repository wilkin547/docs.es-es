---
title: "Object (Tipo de datos) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Object"
  - "vb.Variant"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], asignar"
  - "Object (tipo de datos)"
  - "Object (tipo de datos), referencia"
  - "variables de objeto, Object (tipo)"
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object (Tipo de datos)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene direcciones que hacen referencia a objetos.  Se puede asignar cualquier tipo de referencia \(cadena, matriz, clase o interfaz\) a una variable `Object`.  Una variable `Object` también puede hacer referencia a datos de cualquier tipo de valor \(numérico, `Boolean`, `Char`, `Date`, estructura o enumeración\).  
  
## Comentarios  
 El tipo de datos `Object` puede señalar a datos de cualquier tipo de datos, incluso cualquier instancia de objeto que su aplicación reconozca.  Utilice `Object` cuando en tiempo de compilación no conoce a qué tipo de datos puede señalar la variable.  
  
 El valor predeterminado de `Object` es `Nothing` \(una referencia nula\).  
  
## Tipos de datos  
 Puede asignar una variable, constante o expresión de cualquier tipo de datos a una variable `Object`.  Para determinar el tipo de datos a los que hace referencia actualmente una variable `Object`, puede utilizar el método <xref:System.Type.GetTypeCode%2A> de la clase <xref:System.Type?displayProperty=fullName>.  Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 El tipo de datos `Object` es un tipo de referencia.  Sin embargo, Visual Basic trata una variable `Object` como un tipo de valor cuando hace referencia a datos de un tipo de valor.  
  
## Almacenamiento  
 Independientemente del tipo de datos al que haga referencia, una variable `Object` no contiene el valor de datos en sí, sino un puntero al valor.  Siempre utiliza cuatro bytes en la memoria del sistema, pero sin incluir el almacenamiento para los datos que representan el valor de la variable.  Debido al código que el puntero utiliza para buscar los datos, las variables `Object` que contienen tipos de valor son de acceso un poco más lento que las variables que tienen un tipo explícito.  
  
## Sugerencias de programación  
  
-   **Consideraciones de interoperabilidad.** Si trabaja con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los tipos de puntero de otros entornos no son compatibles con el tipo `Object` de Visual Basic.  
  
-   **Rendimiento.** Una variable que declara con el tipo `Object` es bastante flexible para contener una referencia a cualquier objeto.  Sin embargo, cuando invoca un método o propiedad en este tipo de variable, se produce siempre el *enlace en tiempo de ejecución*.  Para forzar el *enlace en tiempo de compilación* y un mejor rendimiento, declare la variable con un nombre de clase específico o conviértala en el tipo de datos específico.  
  
     Cuando declara una variable de objeto, intente utilizar un tipo de clase concreto, por ejemplo <xref:System.OperatingSystem>, en lugar del tipo `Object` generalizado.  También es preferible utilizar la clase más específica disponible, como <xref:System.Windows.Forms.TextBox> en lugar de <xref:System.Windows.Forms.Control>, así podrá tener acceso a sus propiedades y métodos.  Normalmente puede utilizar la lista **Clases** del **Explorador de objetos** para buscar nombres de clase disponibles.  
  
-   **Ampliación.** Todos los tipos de datos y todos los tipos de referencia se amplían al tipo de datos `Object`.  Esto significa que se puede convertir cualquier tipo a `Object` sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
     Sin embargo, si convierte entre tipos de valor y `Object`, Visual Basic realiza unas operaciones llamadas *conversión boxing* y *conversión unboxing*, que ralentizan la ejecución.  
  
-   **Caracteres de tipo.** `Object` no tiene caracteres de tipo literal ni caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la clase <xref:System.Object?displayProperty=fullName>.  
  
## Ejemplo  
 El ejemplo siguiente ilustra una variable `Object` que señala a una instancia de objeto.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## Vea también  
 <xref:System.Object>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Cómo: Determinar si dos objetos están relacionados](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Cómo: Determinar si dos objetos son idénticos](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)