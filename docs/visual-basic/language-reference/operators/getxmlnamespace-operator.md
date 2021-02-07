---
description: 'Más información sobre: operador GetXmlNamespace (Visual Basic)'
title: Operador GetXmlNamespace
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 704ac22493a0d6ce1255d171ae3b418313b74f09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665918"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace (Operador) (Visual Basic)

Obtiene el <xref:System.Xml.Linq.XNamespace> objeto que corresponde al prefijo de espacio de nombres XML especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Partes  

 `xmlNamespacePrefix`  
 Opcional. Cadena que identifica el prefijo del espacio de nombres XML. Si se proporciona, esta cadena debe ser un identificador XML válido. Para obtener más información, vea [nombres de elementos y atributos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado. Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.  
  
## <a name="return-value"></a>Valor devuelto  

 <xref:System.Xml.Linq.XNamespace>Objeto que corresponde al prefijo del espacio de nombres XML.  
  
## <a name="remarks"></a>Observaciones  

 El `GetXmlNamespace` operador obtiene el <xref:System.Xml.Linq.XNamespace> objeto que corresponde al prefijo del espacio de nombres XML `xmlNamespacePrefix` .  
  
 Puede usar prefijos de espacio de nombres XML directamente en literales XML y propiedades de eje XML. Sin embargo, debe usar el `GetXmlNamespace` operador para convertir un prefijo de espacio de nombres en un <xref:System.Xml.Linq.XNamespace> objeto antes de poder usarlo en el código. Puede anexar un nombre de elemento no calificado a un <xref:System.Xml.Linq.XNamespace> objeto para obtener un <xref:System.Xml.Linq.XName> objeto completo, que requieren muchos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] métodos.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se importa `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario que tiene el nombre completo `ns:phone` . A continuación, pasa ese nodo secundario a la `ShowName` subrutina, que construye un nombre completo mediante el `GetXmlNamespace` operador. `ShowName`A continuación, la subrutina pasa el nombre completo al <xref:System.Xml.Linq.XNode.Ancestors%2A> método para obtener el `ns:contact` nodo primario.  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 Cuando se llama a `TestGetXmlNamespace.RunSample()` , se muestra un cuadro de mensaje que contiene el texto siguiente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vea también

- [Imports (Instrucción, Espacio de nombres XML)](../statements/imports-statement-xml-namespace.md)
- [Obtener acceso a XML en Visual Basic](../../programming-guide/language-features/xml/accessing-xml.md)
