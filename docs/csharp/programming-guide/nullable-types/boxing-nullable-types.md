---
title: "Aplicar la conversi&#243;n boxing a tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "boxing (conversión) [C#], tipos que aceptan valores NULL"
  - "tipos que aceptan valores NULL [C#], boxing y unboxing"
  - "unboxing (conversión) [C#], tipos que aceptan valores NULL"
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Aplicar la conversi&#243;n boxing a tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La conversión boxing sólo se aplica a los objetos basados en tipos que aceptan valores NULL si el valor del objeto no es null.  Si <xref:System.Nullable%601.HasValue%2A> es `false`, la referencia de objeto se asigna a `null` en lugar de aplicar la conversión boxing  Por ejemplo:  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Si el objeto no es NULL \(si <xref:System.Nullable%601.HasValue%2A> es `true`\), tiene lugar la conversión boxing, pero sólo se aplica al tipo subyacente en el que se basa el objeto que acepta valores NULL.  La conversión boxing de un tipo de valor no NULL que acepta valores NULL se aplica al propio tipo de valor, no al objeto <xref:System.Nullable%601?displayProperty=fullName> que ajusta el tipo de valor.  Por ejemplo:  
  
```  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 Los dos objetos a los que se aplica la conversión boxing son idénticos a aquellos creados aplicando la conversión boxing a tipos que no aceptan valores NULL.  Además, al igual que los tipos sin conversión boxing que aceptan valores NULL, se les puede aplicar la conversión unboxing en los tipos que aceptan valores NULL, como en el ejemplo siguiente:  
  
```  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## Comentarios  
 El comportamiento de los tipos que aceptan valores NULL cuando se aplica la conversión boxing proporciona dos ventajas:  
  
1.  Se comprueba si los objetos que aceptan valores NULL y sus homólogos a los que se aplica la conversión boxing tienen valores NULL:  
  
    ```  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  Los tipos que aceptan valores NULL y a los que se aplica la conversión boxing admiten la funcionalidad del tipo subyacente:  
  
    ```  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Cómo: Identificar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)