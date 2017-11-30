---
title: "Cómo: analizar una cadena (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10b80c72cae70437ff812c4b67b2532d708f1e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-parse-a-string-visual-basic"></a>Cómo: analizar una cadena (Visual Basic)
Este tema muestra cómo crear un árbol XML en C#.  
  
## <a name="example"></a>Ejemplo  
 Puede analizar una cadena en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] utilizando el `XElement.Parse` método. Sin embargo, resulta más eficaz usar literales XML, tal como se muestra en el código siguiente, ya que dichos literales no sufren las mismas pérdidas de rendimiento que se producen al analizar XML de una cadena.  
  
 Mediante los literales XML, puede copiar y pegar XML en el programa de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
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
 [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
