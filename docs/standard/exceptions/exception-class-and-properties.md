---
title: Clase Exception y propiedades
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, Exception class
- Exception class
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 253a9846e484aa4e54c3433b0bbc8623519bbb7e
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="exception-class-and-properties"></a>Clase Exception y propiedades

La clase <xref:System.Exception> es la clase base de la que heredan las excepciones. Por ejemplo, la jerarquía de clases de <xref:System.InvalidCastException> es como sigue:

```
Object
  Exception
    SystemException
       InvalidCastException
```

La clase <xref:System.Exception> tiene las siguientes propiedades que facilitan la comprensión de una excepción.

| Nombre de la propiedad | Descripción |
| ------------- | ----------- |
| <xref:System.Exception.Data> | Un <xref:System.Collections.IDictionary> que contiene datos arbitrarios en pares de clave y valor. |
| <xref:System.Exception.HelpLink> | Puede contener una dirección URL (o URN) a un archivo de ayuda que proporciona amplia información sobre la causa de una excepción. |
| <xref:System.Exception.InnerException> | Esta propiedad puede usarse para crear y mantener una serie de excepciones durante el control de excepciones. Puede usarla para crear una nueva excepción que contiene excepciones detectadas con anterioridad. La segunda excepción en la propiedad <xref:System.Exception.InnerException> puede capturar la excepción original, lo que permite que el código que controla la segunda excepción examine la información adicional. Por ejemplo, supongamos que tiene un método que recibe un argumento que contiene un formato incorrecto.  El código intenta leer el argumento, pero se inicia una excepción. El método detecta la excepción e inicia <xref:System.FormatException>. Para mejorar la capacidad del autor de llamada a la hora de determinar por qué se inicia una excepción, a veces, para un método es recomendable detectar una excepción iniciada por una rutina auxiliar y, después, iniciar una excepción más indicativa del error que se ha producido. Puede crear una excepción nueva y más significativa, donde se puede establecer la referencia a la excepción interna en la excepción original. Después, se puede iniciar esta excepción más significativa para el autor de llamada. Tenga en cuenta que con esta funcionalidad, puede crear una serie de excepciones vinculadas que termina con la excepción que se inicia en primer lugar. |
| <xref:System.Exception.Message> | Proporciona detalles sobre la causa de una excepción.
| <xref:System.Exception.Source> | Devuelve o establece el nombre de la aplicación o del objeto que generó el error. |
| <xref:System.Exception.StackTrace>| Contiene un seguimiento de la pila que puede usarse para determinar dónde se produjo un error. El seguimiento de la pila contiene el nombre del archivo de código fuente y el número de línea del programa si está disponible la información de depuración. |

La mayoría de las clases que heredan de <xref:System.Exception> no implementan miembros adicionales ni proporcionan funciones adicionales; simplemente heredan de <xref:System.Exception>. Por tanto, se puede encontrar la información más importante para una excepción en la jerarquía de clases de excepción, el nombre de la excepción y la información contenida en la excepción.

Se recomienda que producir y detectar solo los objetos que derivan de <xref:System.Exception>, pero se puede producir cualquier objeto que se deriva de la <xref:System.Object> clase como una excepción. Tenga en cuenta que no todos los lenguajes admiten iniciar y detectar objetos que no se derivan de <xref:System.Exception>.
  
## <a name="see-also"></a>Vea también  
[Excepciones](index.md)
