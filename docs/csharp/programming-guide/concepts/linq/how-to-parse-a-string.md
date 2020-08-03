---
title: Procedimiento para analizar una cadena (C#)
description: Aprenda a analizar una cadena para crear un árbol XML en C#. Aprenda a acceder a datos específicos del XML analizado.
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: a4664e090b6a44c52c519e61b66ccdc5d59a71f1
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104808"
---
# <a name="how-to-parse-a-string-c"></a>Procedimiento para analizar una cadena (C#)

En este tema se muestra cómo analizar una cadena para crear un árbol XML en C#.

## <a name="example"></a>Ejemplo

El siguiente código de C# muestra cómo analizar una cadena XML:

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

El nodo `Contacts` raíz tiene dos nodos `Contact`. Para acceder a algunos datos específicos en su XML analizado, use el método [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements), que en este caso devuelve los elementos secundarios del nodo raíz `Contacts`. En el siguiente ejemplo se imprime el primer nodo `Contact` en la consola:

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a>Consulte también

- [Procedimiento para buscar un elemento con un atributo específico (C#)](how-to-find-an-element-with-a-specific-attribute.md)
