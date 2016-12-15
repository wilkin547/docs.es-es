---
title: "Campos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "campos [C#]"
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Campos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un *campo* es una variable de cualquier tipo que se declara directamente en una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md).  Los campos son *miembros* de su tipo contenedor.  
  
 Una clase o struct puede tener campos de instancia, campos estáticos o ambos.  Los campos de instancia son específicos de una instancia de un tipo.  Si tiene una clase T, con un campo de instancia F, puede crear dos objetos de tipo T y modificar el valor de F en cada objeto sin afectar al valor del otro objeto.  Por el contrario, un campo estático pertenece a la propia clase y se comparte entre todas las instancias de dicha clase.  Los cambios realizados en la instancia A serán inmediatamente visibles en las instancias B y C si tienen acceso al campo.  
  
 Por regla general, solo debe utilizar campos para variables con accesibilidad privada o protegida.  Los datos que la clase expone al código de cliente se deben proporcionar a través de [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md) e [indizadores](../../../csharp/programming-guide/indexers/index.md).  Si se utilizan estas construcciones para el acceso indirecto a campos internos, se establece una protección ante valores de entrada no válidos.  Un campo privado que almacena los datos expuestos por una propiedad pública se denomina *memoria auxiliar* o *campo de respaldo*.  
  
 Habitualmente los campos almacenan los datos a los que deben tener acceso más de un método de clase y que se deben almacenar durante más tiempo que el período de duración de un único método.  Por ejemplo, una clase que representa una fecha del calendario podría tener tres campos enteros: uno para el mes, otro para el día y un tercero para el año.  Las variables que no se utilizan fuera del ámbito de un único método se deben declarar como *variables locales* dentro del propio cuerpo del método.  
  
 Los campos se declaran en el bloque de clase especificando el nivel de acceso del campo, seguido por el tipo de campo y después por el nombre del mismo.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]  
  
 Para obtener acceso a un campo en un objeto, agregue un punto después del nombre de objeto, seguido del nombre del campo, como en `objectname.fieldname`.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]  
  
 Se puede proporcionar un valor inicial a un campo utilizando el operador de asignación cuando se declara el campo.  Para asignar automáticamente al campo `day` el valor `"Monday"`, por ejemplo, declararía `day` como en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]  
  
 Los campos se inicializan inmediatamente antes de llamar al constructor para la instancia de objeto.  Si el constructor asigna el valor de un campo, sobrescribirá cualquier valor dado durante la declaración del campo.  Para obtener más información, vea [Utilizar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md).  
  
> [!NOTE]
>  Un inicializador de campo no puede hacer referencia a campos de otra instancia.  
  
 Los campos se pueden marcar como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected internal`.  Estos modificadores de acceso definen cómo pueden tener acceso a los campos los usuarios de la clase.  Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Un campo puede declararse de forma opcional como [static](../../../csharp/language-reference/keywords/static.md).  Esto hace que el campo esté siempre disponible para los llamadores, aunque no exista ninguna instancia de la clase.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Un campo puede declararse como [readonly](../../../csharp/language-reference/keywords/readonly.md).  Solo es posible asignar un valor a un campo de tipo readonly durante la inicialización o en un constructor.  Un campo `static` `readonly` es muy similar a una constante, excepto en que el compilador de C\# no tiene acceso a él en tiempo de compilación, solo en tiempo de ejecución.  Para obtener más información, vea [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Utilizar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)