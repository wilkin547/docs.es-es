---
title: "Tipo de datos definido por el usuario | Microsoft Docs"
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
  - "UserDefined"
  - "UDT"
  - "vb.UDT"
  - "User-Defined"
  - "vb.UserDefined"
  - "vb.User-Defined"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], asignar"
  - "tipos de datos [Visual Basic], definidos por el usuario"
  - "Structure (instrucción)"
  - "estructuras, como tipos de datos definidos por el usuario"
  - "tipos [Visual Basic], definidos por el usuario"
  - "tipos de datos definidos por el usuario"
  - "tipos de datos definidos por el usuario, declaración de estructura"
  - "tipos de datos definidos por el usuario, estructuras en Visual Basic"
  - "tipos de datos definidos por el usuario, Visual Basic"
  - "tipos definidos por el usuario"
  - "tipos definidos por el usuario, declaración de estructura"
  - "tipos definidos por el usuario, estructuras en Visual Basic"
  - "tipos definidos por el usuario, Visual Basic"
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipo de datos definido por el usuario
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene los datos en el formato que defina el usuario.  La instrucción `Structure` define el formato.  
  
 Las versiones anteriores de Visual Basic admitían el tipo definido por el usuario \(UDT\).  La versión actual amplía el tipo definido por el usuario a una *estructura*.  Una estructura es una concatenación de uno o varios *miembros* de diversos tipos de datos.  Visual Basic trata una estructura como una unidad única, aunque también puede tener acceso individualmente a sus miembros.  
  
## Comentarios  
 Defina y utilice un tipo de datos de estructura cuando necesite combinar varios tipos de datos en una única unidad o cuando ninguno de los tipos de datos básicos satisfaga sus necesidades.  
  
 El valor predeterminado de un tipo de datos de estructura se compone de la combinación de valores predeterminados de cada uno de sus miembros.  
  
## Formato de declaración  
 Una declaración de estructura se inicia con la instrucción [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md) y finaliza con la instrucción `End` `Structure`.  La instrucción `Structure` proporciona el nombre de la estructura, que también actúa como identificador del tipo de datos que está definiendo la estructura.  Otras partes del código pueden utilizar este identificador para declarar variables, parámetros y valores devueltos de la función para que pertenezca al tipo de datos de esta estructura.  
  
 Las declaraciones comprendidas entre las instrucciones `Structure` y `End``Structure` definen los miembros de la estructura.  
  
## Niveles de acceso a miembros  
 Debe declarar cada miembro utilizando una instrucción [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md) o una instrucción que especifique el nivel de acceso, como [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md) o [Private](../../../visual-basic/language-reference/modifiers/private.md).  Si utiliza una instrucción `Dim`, el nivel de acceso es público de manera predeterminada.  
  
## Sugerencias de programación  
  
-   **Consumo de memoria.** Como en los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros.  Es más, no puede suponerse que el orden de almacenamiento en la memoria sea el mismo que el orden de la declaración.  Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.  
  
-   **Consideraciones de interoperabilidad.** Si está interactuando con componentes que no se han escrito para .NET Framework, por ejemplo objetos de automatización u objetos COM, tenga presente que los tipos de datos definidos por el usuario en otros entornos no son compatibles con los tipos de estructuras de Visual Basic.  
  
-   **Ampliación.** No existen conversiones automáticas a un tipo de datos de estructuras o desde un tipo de datos de estructuras.  Puede definir operadores de conversión en la estructura utilizando [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md) y puede declarar cada operador de conversión para que sea `Widening` o `Narrowing`.  
  
-   **Caracteres de tipo.** Los tipos de datos de estructura no tienen ningún carácter de tipo literal ni ningún carácter de tipo identificador.  
  
-   **Tipo en Framework.** No hay ningún tipo correspondiente en .NET Framework.  Todas las estructuras se heredan de la clase de .NET Framework <xref:System.ValueType?displayProperty=fullName>, pero ninguna estructura individual se corresponde con <xref:System.ValueType?displayProperty=fullName>.  
  
## Ejemplo  
 En el siguiente modelo se muestra el esquema de declaración de una estructura.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## Vea también  
 <xref:System.ValueType>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)