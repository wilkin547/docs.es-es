---
title: Compatibilidad de identificadores de recursos internacionales en System.Uri
ms.date: 03/30/2017
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
ms.openlocfilehash: f78fff250aae177b5f0360e77a1c41a2f2bb0527
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "64647335"
---
# <a name="international-resource-identifier-support-in-systemuri"></a>Compatibilidad de identificadores de recursos internacionales en System.Uri
La clase <xref:System.Uri?displayProperty=nameWithType> se ha ampliado con la compatibilidad con Identificadores de recursos internacionales (IRI) y Nombres de dominio internacionalizados (IDN). Estas mejoras están disponibles en .NET Framework 3.5, 3.0 SP1 y 2.0 SP1.  
  
## <a name="iri-and-idn-support"></a>Compatibilidad con IRI e IDN  
 Las direcciones web normalmente se expresan mediante identificadores uniformes de recursos (URI), que consisten en un conjunto muy restringido de caracteres:  
  
- Letras ASCII mayúsculas y minúsculas del alfabeto inglés.  
  
- Dígitos del 0 al 9.  
  
- Un número reducido de otros símbolos ASCII.  
  
 Las especificaciones para los URI están documentadas en RFC 2396 y RFC 3986, publicados por Internet Engineering Task Force (IETF).  
  
 Debido a la expansión de Internet, hay una creciente necesidad de identificar los recursos mediante el uso de idiomas distintos del inglés. Los identificadores que responden a esta necesidad y permiten caracteres que no son ASCII (caracteres del juego de caracteres Unicode/ISO 10646) se conocen como Identificadores de recursos internacionales (IRI). Las especificaciones de los IRI están documentadas en RFC 3987, publicado por el IETF. El uso de IRI permite que una dirección URL contenga caracteres Unicode.  
  
 La clase <xref:System.Uri?displayProperty=nameWithType> existente se ha ampliado para proporcionar compatibilidad con IRI basada en RFC 3987. Los usuarios actuales no percibirán ningún cambio respecto al comportamiento de .NET Framework 2.0, a menos que habiliten IRI específicamente. Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.  
  
 Una aplicación puede especificar si se debe usar el análisis del Nombre de dominio internacionalizado (IDN) aplicado a nombres de dominio y si deben aplicarse reglas de análisis de IRI. Esto puede hacerse en el archivo machine.config o app.config.  
  
 La activación de IDN convertirá todas la etiquetas Unicode de un nombre de dominio en sus equivalentes de Punycode. Los nombres de Punycode solo contienen caracteres ASCII y siempre empiezan con el prefijo xn--. De este modo, se admiten los servidores DNS existentes en Internet, ya que la mayoría de los servidores DNS solo admite caracteres ASCII (vea RFC 3940).  
  
 La activación de IRI e IDN afecta al valor de la propiedad <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>. Cuando se habilitan IRI e IDN, también puede cambiar el comportamiento de los métodos <xref:System.Uri.Equals%2A?displayProperty=nameWithType>, <xref:System.Uri.OriginalString%2A?displayProperty=nameWithType>, <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType> y <xref:System.Uri.IsWellFormedOriginalString%2A>.  
  
 La clase <xref:System.GenericUriParser?displayProperty=nameWithType> también se ha ampliado para permitir la creación de un analizador personalizable que admita IRI e IDN. Para especificar el comportamiento de un objeto <xref:System.GenericUriParser?displayProperty=nameWithType>, se pasa una combinación bit a bit de los valores disponibles en la enumeración <xref:System.GenericUriParserOptions?displayProperty=nameWithType> al constructor <xref:System.GenericUriParser?displayProperty=nameWithType>. El tipo <xref:System.GenericUriParserOptions.IriParsing?displayProperty=nameWithType> indica que el analizador admite las reglas de análisis especificadas en RFC 3987 para los Identificadores de recursos internacionales (IRI). Para que IRI se use realmente, es necesario habilitarlo.  
  
 El tipo <xref:System.GenericUriParserOptions.Idn?displayProperty=nameWithType> indica que el analizador admite el análisis del Nombre de dominio internacionalizado (IDN) de los nombres de host. Para que IDN se use realmente, es necesario habilitarlo.  
  
 Al habilitar el análisis de IRI, se efectuarán comprobaciones de normalización y caracteres conforme a las normas más recientes sobre IRI indicadas en RFC 3987. Según el valor predeterminado, el análisis de IRI está deshabilitado para que la comprobación de normalización y caracteres se realice según RFC 2396 y RFC 3986.  
  
 El procesamiento de IRI e IDN en la clase <xref:System.Uri?displayProperty=nameWithType> también se puede controlar mediante las clases de valores de configuración <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> y <xref:System.Configuration.IdnElement?displayProperty=nameWithType>. El valor <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> habilita o deshabilita el procesamiento de IRI en la clase <xref:System.Uri?displayProperty=nameWithType>. El valor <xref:System.Configuration.IdnElement?displayProperty=nameWithType> habilita o deshabilita el procesamiento de IDN en la clase <xref:System.Uri>. El valor <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> también controla indirectamente IDN. El procesamiento de IRI debe estar habilitado para que el procesamiento de IDN sea posible. Si el procesamiento de IRI está deshabilitado, el procesamiento de IDN se establecerá en el valor predeterminado, según el cual se usa el comportamiento de .NET Framework 2.0 para la compatibilidad y no se usan nombres IDN.  
  
 El valor de configuración para las clases de configuración <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> y <xref:System.Configuration.IdnElement?displayProperty=nameWithType> se leerá una vez cuando se construya la primera clase <xref:System.Uri?displayProperty=nameWithType>. Después, se omitirán los cambios realizados en los valores de configuración.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>
