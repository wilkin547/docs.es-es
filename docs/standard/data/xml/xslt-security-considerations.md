---
title: "Consideraciones de seguridad de XSLT | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: fea695be-617c-4977-9567-140e820436fc
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Consideraciones de seguridad de XSLT
El lenguaje XSLT posee un amplio conjunto de características que aportan gran potencia y flexibilidad.  Incluye muchas características que, aunque son útiles, también se podrían aprovechar desde orígenes externos.  Para poder utilizar XSLT con seguridad, debe conocer los tipos de problemas de seguridad que surgen al utilizar XSLT y las estrategias básicas que puede emplear para mitigar estos riesgos.  
  
## Extensiones XSLT  
 Dos extensiones XSLT conocidas son los objetos de extensión y el scripting de hoja de estilos.  Estas extensiones permiten al procesador XSLT ejecutar código.  
  
-   Los objetos de extensión agregan capacidades de programación a las transformaciones XSL.  
  
-   Los scripts se pueden incrustar en la hoja de estilos utilizando el elemento de extensión `msxsl:script`.  
  
### Objetos de extensión  
 Los objetos de extensión se agregan con el método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.  Se requiere el conjunto de permisos FullTrust para admitir los objetos de extensión.  De esta manera, se garantiza que no se produzca una elevación de permisos cuando se ejecuta el código de objetos de extensión.  Al intentar llamar al método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> sin permisos FullTrust, se produce el inicio de una excepción de seguridad.  
  
### Scripts de hoja de estilos  
 Los scripts se pueden incrustar en una hoja de estilos utilizando el elemento de extensión `msxsl:script`.  La compatibilidad con scripts es una característica opcional en la clase <xref:System.Xml.Xsl.XslCompiledTransform> que está deshabilitada de manera predeterminada.  Los scripts se pueden habilitar estableciendo la propiedad <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A?displayProperty=fullName> en `true` y pasando el objeto <xref:System.Xml.Xsl.XsltSettings> al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
#### Instrucciones  
 Únicamente habilite los scripts cuando la hoja de estilos provenga de un origen de confianza.  Si no puede comprobar el origen de la hoja de estilos, o si la hoja de estilos no proviene de un origen de confianza, pase `null` pase el argumento de valores de XSLT.  
  
## Recursos externos  
 El lenguaje XSLT tiene características como, por ejemplo, `xsl:import`, `xsl:include` o la función `document()`, en las que el procesador tiene que resolver referencias de URI.  La clase <xref:System.Xml.XmlResolver> se utiliza para resolver recursos externos.  Puede que haya que resolver los recursos externos en los siguientes dos casos:  
  
-   Al compilar una hoja de estilos, el <xref:System.Xml.XmlResolver> se utiliza para la resolución de `xsl:import` y `xsl:include`.  
  
-   Al ejecutar la transformación, <xref:System.Xml.XmlResolver> se utiliza para resolver la función `document()`.  
  
    > [!NOTE]
    >  La función `document()` se deshabilita de manera predeterminada en la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  Esta característica se puede habilitar estableciendo la propiedad <xref:System.Xml.Xsl.XsltSettings.EnableDocumentFunction%2A?displayProperty=fullName> en `true` y pasando el objeto <xref:System.Xml.Xsl.XsltSettings> al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
 Los métodos <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> y <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> incluyen sobrecargas que aceptan un objeto <xref:System.Xml.XmlResolver> como uno de sus argumentos.  Si no se especifica un código <xref:System.Xml.XmlResolver>, se utiliza una referencia <xref:System.Xml.XmlUrlResolver> predeterminada sin ninguna credencial.  
  
#### Instrucciones  
 Únicamente habilite la función `document()` cuando la hoja de estilos provenga de un origen de confianza.  
  
 En la siguiente lista se describe cuándo es conveniente especificar un objeto <xref:System.Xml.XmlResolver>:  
  
-   Si el proceso XSLT necesita tener acceso a un recurso de red que requiere autenticación, puede utilizar un <xref:System.Xml.XmlResolver> con las credenciales necesarias.  
  
-   Si desea restringir los recursos a los que tiene acceso el proceso XSLT, puede utilizar un <xref:System.Xml.XmlSecureResolver> con el conjunto de permisos correcto.  Utilice la clase <xref:System.Xml.XmlSecureResolver> si necesita abrir un recurso que no controla o que no es de confianza.  
  
-   Si desea personalizar el comportamiento, puede implementar su propia clase <xref:System.Xml.XmlResolver> y utilizarla para resolver recursos.  
  
-   Si desea asegurarse de que no se tiene acceso a ningún recurso externo, puede especificar `null` para el argumento <xref:System.Xml.XmlResolver>.  
  
## Vea también  
 [Transformaciones XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)   
 [Resolución de recursos externos durante el procesamiento XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)   
 [Code Access Security](http://msdn.microsoft.com/es-es/23a20143-241d-4fe5-9d9f-3933fd594c03)