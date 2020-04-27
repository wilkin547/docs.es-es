---
title: Resolución de recursos externos durante el procesamiento XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 58407d5f0c6e602af15f5b19b9a19cc6379b9af7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710289"
---
# <a name="resolving-external-resources-during-xslt-processing"></a>Resolución de recursos externos durante el procesamiento XSLT
Hay varios momentos a lo largo de una transformación XSLT en los cuales puede que necesite resolver recursos externos.  
  
## <a name="using-the-xmlresolver-class"></a>Utilizar la clase XmlResolver  
 La clase <xref:System.Xml.XmlResolver> se utiliza para resolver recursos externos. En la siguiente tabla se describe cuándo <xref:System.Xml.XmlResolver> se implica en el procesamiento XSLT.  
  
|Tarea de XSLT|XmlResolver se utiliza para|  
|---------------|--------------------------------------|  
|Compilar la hoja de estilos.|Resolver el identificador URI de la hoja de estilos.<br /><br /> \- y -<br /><br /> Resolver referencias URI en cualquier elemento `xsl:import` o `xsl:include`.|  
|Ejecutar la hoja de estilos.|Resolver el identificador URI del documento de contexto.<br /><br /> \- y -<br /><br /> Resolver referencias URI en cualquier función `document()` de XSLT.|  
  
 Los métodos <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> y <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> incluyen sobrecargas que toman un objeto <xref:System.Xml.XmlResolver> como uno de sus argumentos. Si no se especifica un código <xref:System.Xml.XmlResolver>, se utiliza una referencia <xref:System.Xml.XmlUrlResolver> predeterminada sin ninguna credencial.  
  
 En la siguiente lista se describe cuándo es conveniente especificar un objeto <xref:System.Xml.XmlResolver>:  
  
- Si el proceso XSLT necesita tener acceso a un recurso de red que requiere autenticación, puede utilizar un <xref:System.Xml.XmlResolver> con las credenciales necesarias.  
  
- Si desea restringir los recursos a los que tiene acceso el proceso XSLT, puede utilizar un <xref:System.Xml.XmlSecureResolver> con el conjunto de permisos correcto. Utilice la clase <xref:System.Xml.XmlSecureResolver> si necesita abrir un recurso que no controla o que no es de confianza.  
  
- Si desea personalizar el comportamiento, puede implementar su propia clase <xref:System.Xml.XmlResolver> y utilizarla para resolver recursos.  
  
- Si desea asegurarse de que no se tiene acceso a ningún recurso externo, puede especificar `null` para el argumento <xref:System.Xml.XmlResolver>.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se compila una hoja de estilos que está almacenada en un recurso de red. Un objeto <xref:System.Xml.XmlUrlResolver> especifica las credenciales necesarias para tener acceso a la hoja de estilos.  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [Transformaciones XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
