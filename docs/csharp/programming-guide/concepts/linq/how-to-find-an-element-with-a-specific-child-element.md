---
title: Procedimiento para buscar un elemento con un elemento secundario específico (C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 6888de3bc255691fbbb05f2a1debae05492661c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547285"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a>Procedimiento para buscar un elemento con un elemento secundario específico (C#)
Este tema muestra cómo encontrar un elemento en particular que tenga un elemento secundario con un valor específico.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo busca el elemento `Test` que tenga un elemento secundario `CommandLine` con el valor de "Examp2.EXE".  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 Este código genera el siguiente resultado:  
  
```  
0002  
0006  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres. Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 Este código genera el siguiente resultado:  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Consultas básicas (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))
- [Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md) (Operaciones de proyección [C#])
