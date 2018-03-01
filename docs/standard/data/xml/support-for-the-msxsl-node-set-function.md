---
title: "Compatibilidad con la función msxsl:node-set()"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7cd79acbdef09acb0a05c818d8358cd612c3bcdf
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="support-for-the-msxslnode-set-function"></a>Compatibilidad con la función msxsl:node-set()
La función `msxsl:node-set` permite convertir un fragmento del árbol de resultados en un conjunto de nodos. El conjunto de nodos resultante siempre contiene un único nodo, que es el nodo raíz del árbol.  
  
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.  
  
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
                <author><xsl:value-of select="@author"/)</author>  
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
 [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
