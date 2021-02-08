---
description: 'Más información acerca de: literal de instrucción de procesamiento XML (Visual Basic)'
title: Literal de instrucción de procesamiento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 5037aab343cbe50ebc48614991e96da8198a481f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787531"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Literal de instrucción de procesamiento XML (Visual Basic)

Literal que representa un <xref:System.Xml.Linq.XProcessingInstruction> objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Partes  

 `<?`  
 Necesario. Denota el inicio del literal de instrucción de procesamiento XML.  
  
 `piName`  
 Necesario. Nombre que indica la aplicación a la que se destina la instrucción de procesamiento. No puede comenzar por "XML" o "XML".  
  
 `piData`  
 Opcional. Cadena que indica cómo la aplicación de destino `piName` debe procesar el documento XML.  
  
 `?>`  
 Necesario. Denota el final de la instrucción de procesamiento.  
  
## <a name="return-value"></a>Valor devuelto  

 Objeto <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Observaciones  

 Los literales de instrucciones de procesamiento XML indican cómo deben procesar las aplicaciones un documento XML. Cuando una aplicación carga un documento XML, la aplicación puede comprobar las instrucciones de procesamiento XML para determinar cómo procesar el documento. La aplicación interpreta el significado de `piName` y `piData` .  
  
 El literal de documento XML utiliza una sintaxis similar a la de la instrucción de procesamiento XML. Para obtener más información, vea [literal de documento XML](xml-document-literal.md).  
  
> [!NOTE]
> El `piName` elemento no puede comenzar con las cadenas "XML" o "XML", ya que la especificación xml 1,0 reserva esos identificadores.  
  
 Puede asignar un literal de instrucción de procesamiento XML a una variable o incluirlo en un literal de documento XML.  
  
> [!NOTE]
> Un literal XML puede abarcar varias líneas sin necesidad de caracteres de continuación de línea. Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.  
  
 El compilador Visual Basic convierte el literal de instrucción de procesamiento XML en una llamada al <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XProcessingInstruction>
- [Literal de documento XML](xml-document-literal.md)
- [Literales XML](index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
