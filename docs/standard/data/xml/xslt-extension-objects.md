---
title: Objetos de extensión de XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40a530190ee4b19d72399ab877cf26bad1090b9f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45649333"
---
# <a name="xslt-extension-objects"></a>Objetos de extensión de XSLT
Los objetos de extensión se utilizan para ampliar la funcionalidad de las hojas de estilos. La clase <xref:System.Xml.Xsl.XsltArgumentList> mantiene los objetos de extensión.  
  
 A continuación se enumeran las ventajas de utilizar un objeto de extensión en lugar de un script incrustado:  
  
-   Proporciona una mejor encapsulación y reutilización de clases.  
  
-   Permite que las hojas de estilos sean más pequeñas y facilita su mantenimiento.  
  
 Los objetos de extensión XSLT se agregan al objeto <xref:System.Xml.Xsl.XsltArgumentList> con el método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. En ese momento se asocian un nombre completo y un identificador URI de espacio de nombres con el objeto de extensión.  
  
> [!NOTE]
>  Se requiere el conjunto de permisos FullTrust para llamar al método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. Para obtener más información, vea [Seguridad de acceso del código](https://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03) y [Conjuntos de permisos con nombre](https://msdn.microsoft.com/library/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).  
  
 Los tipos de datos devueltos desde los objetos de extensión pertenecen a uno de los cuatro tipos de datos básicos de Xpath: `number`, `string`, `Boolean` y `node set`.  
  
 Cualquier método que se defina con la palabra clave `params`, que permite pasar un número no especificado de parámetros, no es compatible actualmente con la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Las hojas de estilos XSLT que utilicen cualquier método definido con la palabra clave `params` no funcionan correctamente. Para obtener información, consulte los [parámetros](~/docs/csharp/language-reference/keywords/params.md).  
  
### <a name="to-use-an-xslt-extension-object"></a>Para utilizar un objeto de extensión XSLT  
  
1.  Cree un objeto <xref:System.Xml.Xsl.XsltArgumentList> y agregue el objeto de extensión utilizando el método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.  
  
2.  Llame al objeto de extensión desde la hoja de estilos.  
  
3.  Pase el objeto <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)  
- [Consideraciones de seguridad de XSLT](../../../../docs/standard/data/xml/xslt-security-considerations.md)
