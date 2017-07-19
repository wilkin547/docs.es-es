---
title: "Compatibilidad de identificadores de recursos internacionales en System.Uri | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Compatibilidad de identificadores de recursos internacionales en System.Uri
La clase de <xref:System.Uri?displayProperty=fullName> se ha extendido con el identificador \(IRI\) y de nombres de dominio Names \(IDN\) de recursos internacionales \(IRI\).  Estas mejoras disponibles en .NET Framework 3.5, 3,0 SP1, y 2,0 SP1.  
  
## Compatibilidad con IRI e IDN  
 Expresan las direcciones web normalmente mediante Identificadores uniformes de recursos \(URI\) que constan de un conjunto muy restringido de caracteres:  
  
-   Letras ASCII mayúsculas y minúsculas del alfabeto inglés.  
  
-   Dígitos de 0 a 9.  
  
-   Un número pequeño de otros símbolos ASCII.  
  
 Las especificaciones para los URI figuran en los documentos RFC 2396 y RFC 3986 publicados por el grupo de trabajo de ingeniería de Internet IETF \(Internet Engineering Task Force\).  
  
 Con el desarrollo de Internet, hay una necesidad creciente de identificar los recursos con idiomas que no sean el inglés.  Los identificadores que facilitan esta necesidad y permiten caracteres distintos de ASCII \(caracteres del juego de caracteres Unicode\/ISO 10646\) se conocen como identificadores de recursos internacionales \(IRI\).  Las especificaciones para los IRI figuran en el documento RFC 3987 publicado por el IETF.  Los IRI permiten que las direcciones URL contengan caracteres Unicode.  
  
 La clase existente de <xref:System.Uri?displayProperty=fullName> se ha extendido para proporcionar IRI admite basado en RFC 3987.  Los usuarios actuales no verán ningún cambio respecto del comportamiento de .NET Framework 2.0, a menos que habiliten específicamente IRI.  De este modo, queda garantizada la compatibilidad de la aplicación con las versiones anteriores de .NET Framework.  
  
 Una aplicación puede especificar si utilizar el análisis de nombres de dominio internacionalizados \(IDN\) aplicado a los nombres de dominio y si las reglas de análisis IRI deben aplicarse.  Esto puede hacerse en el archivo machine.config o app.config.  
  
 Al habilitar IDN, todas las etiquetas Unicode de un nombre de dominio se convertirán en sus equivalentes Punycode.  Los nombres Punycode sólo contienen caracteres ASCII y siempre empiezan con el prefijo xn\-\-.  De este modo, se proporciona compatibilidad con los servidores DNS existentes en Internet, dado que la mayoría de estos servidores sólo admiten caracteres ASCII \(vea RFC 3940\).  
  
 Al habilitar IRI e IDN, el valor de la propiedad <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName> se ve afectado.  Al habilitar IRI e IDN, también puede cambiar el comportamiento de los métodos <xref:System.Uri.Equals%2A?displayProperty=fullName>, <xref:System.Uri.OriginalString%2A?displayProperty=fullName>, <xref:System.Uri.GetComponents%2A?displayProperty=fullName> e <xref:System.Uri.IsWellFormedOriginalString%2A>.  
  
 La clase <xref:System.GenericUriParser?displayProperty=fullName> también se ha extendido para permitir la creación de un analizador personalizable que admita IRI e IDN.  El comportamiento de un objeto <xref:System.GenericUriParser?displayProperty=fullName> se especifica pasando al constructor de <xref:System.GenericUriParser?displayProperty=fullName> una combinación bit a bit de los valores disponibles en la enumeración de <xref:System.GenericUriParserOptions?displayProperty=fullName>.  El tipo <xref:System.GenericUriParserOptions?displayProperty=fullName> indica que el analizador admite las reglas de análisis especificadas en RFC 3987 para los identificadores de recursos internacionales \(IRI\).  Si IRI se utiliza realmente depende de si se habilita IRI.  
  
 El tipo <xref:System.GenericUriParserOptions?displayProperty=fullName> indica que el analizador admite el análisis IDN \(Nombres de dominio internacionalizados\) de los nombres de host.  Si IDN se utiliza realmente depende de si está habilitado el IDN.  
  
 Habilitar el análisis IRI hará la normalización y la comprobación de caracteres se realizarán de acuerdo con las últimas reglas IRI de RFC 3987.  El valor predeterminado es para IRI que analiza para deshabilitar para que la comprobación de la normalización y de caracteres se hace según RFC 2396 y RFC 3986.  
  
 El procesamiento IRI e IDN en la clase de <xref:System.Uri?displayProperty=fullName> también se puede controlar mediante clases de la opción de configuración de <xref:System.Configuration.IriParsingElement?displayProperty=fullName> y de <xref:System.Configuration.IdnElement?displayProperty=fullName> .  El valor <xref:System.Configuration.IriParsingElement?displayProperty=fullName> habilita o deshabilita el procesamiento de IRI en la clase <xref:System.Uri?displayProperty=fullName>.  El valor <xref:System.Configuration.IdnElement?displayProperty=fullName> habilita o deshabilita el procesamiento de IDN en la clase <xref:System.Uri>.  El valor <xref:System.Configuration.IriParsingElement?displayProperty=fullName> también controla IDN indirectamente.  El procesamiento IRI debe estar habilitado para que el procesamiento IDN sea posible.  Si el procesamiento IRI está deshabilitado, el procesamiento IDN se establece en el valor predeterminado, donde se usa el comportamiento de .NET Framework 2.0 por motivos de compatibilidad y no se usan los nombres IDN.  
  
 La opción de configuración para las clases de configuración de <xref:System.Configuration.IriParsingElement?displayProperty=fullName> y de <xref:System.Configuration.IdnElement?displayProperty=fullName> se lea una vez cuando se crea la primera clase de <xref:System.Uri?displayProperty=fullName> .  Después de ese momento, se omitirán los cambios que se produzcan en los valores de configuración.  
  
## Vea también  
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName>