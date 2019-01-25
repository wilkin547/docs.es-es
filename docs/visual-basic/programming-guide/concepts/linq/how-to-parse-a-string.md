---
title: Procedimiento Analizar una cadena (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 513a82cbed796be42eb8e531ec71221ef0ac267f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652454"
---
# <a name="how-to-parse-a-string-visual-basic"></a>Procedimiento Analizar una cadena (Visual Basic)
En este tema se muestra cómo crear un árbol XML en C#.  
  
## <a name="example"></a>Ejemplo  
 Puede analizar una cadena en Visual Basic mediante la `XElement.Parse` método. Sin embargo, resulta más eficaz usar literales XML, tal como se muestra en el código siguiente, ya que dichos literales no sufren las mismas pérdidas de rendimiento que se producen al analizar XML de una cadena.  
  
 Mediante literales XML, puede simplemente copiar y pegar el código XML en el programa de Visual Basic.  
  
> [!NOTE]
>  Analizar texto o cargar un documento XML de un archivo de texto es menos eficaz que la construcción funcional. Si inicializa un árbol XML a partir de código, el uso de la construcción funcional consume menos tiempo de procesador que el análisis de texto.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
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
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>Vea también
- [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
