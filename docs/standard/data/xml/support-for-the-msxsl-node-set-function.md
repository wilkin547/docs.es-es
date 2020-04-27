---
title: Compatibilidad con la función msxsl:node-set()
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 5022b298cb20796edbc54e951d8b06043697d832
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155599"
---
# <a name="support-for-the-msxslnode-set-function"></a>Compatibilidad con la función msxsl:node-set()
La función `msxsl:node-set` permite convertir un fragmento del árbol de resultados en un conjunto de nodos. El conjunto de nodos resultante siempre contiene un único nodo, que es el nodo raíz del árbol.  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 La función `msxsl:node-set` permite convertir un fragmento del árbol de resultados en un conjunto de nodos. El conjunto de nodos resultante siempre contiene un único nodo, que es el nodo raíz del árbol.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `$var` es una variable que es un árbol de nodos en la hoja de estilos. La instrucción for-each, combinada con la función `node-set`, permite que el usuario itere por este árbol como un conjunto de nodos.  
  
## <a name="nodesetxsl"></a>nodeset.xsl  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">
                <author><xsl:value-of select="@author"/></author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a>Salida  
 El resultado de la transformación es  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
