---
title: "Revisi&#243;n de adaptabilidad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicaciones de uso internacional, localizabilidad"
  - "desarrollo de aplicaciones [.NET Framework], localización"
  - "localizabilidad [.NET Framework]"
  - "aplicaciones internacionales [.NET Framework], localizabilidad"
  - "globalización [.NET Framework], localizabilidad"
  - "cultura, localizabilidad"
  - "localización [.NET Framework], localizabilidad"
  - "aplicaciones globales, localizabilidad"
  - "adaptar recursos"
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Revisi&#243;n de adaptabilidad
La revisión de localización es un paso intermedio en el desarrollo de una aplicación de uso internacional.  Comprueba que una aplicación globalizada está preparada para la localización e identificar cualquier código o los aspectos de la interfaz de usuario que requieren un tratamiento especial.  Este paso también ayuda a garantizar que el proceso de localización no se introducirán ninguna defectos funcional en la aplicación.  Cuando todos los problemas provocados por la revisión de localización se han resuelto, la aplicación está preparada para la localización.  Si la revisión de localización está lleno, no debería tener que modificar ningún código fuente durante el proceso de localización.  
  
 La revisión de localización consta de las tres comprobaciones siguientes:  
  
-   [¿Se implementan las recomendaciones de globalización?](#global)  
  
-   [¿Las características cultura\- confidenciales se controlan correctamente?](#culture)  
  
-   [¿Se ha probado la aplicación con datos internacionales?](#test)  
  
<a name="global"></a>   
## Implementar recomendaciones de globalización  
 Si ha diseñado y ha desarrollado la aplicación teniendo en cuenta la localización, y si ha seguido las recomendaciones descritas en el caso de [Globalización](../../../docs/standard/globalization-localization/globalization.md) , la revisión de localización estará en gran medida un paso de control de calidad.  Si no, durante esta fase debe revisar e implementar recomendaciones para [globalización](../../../docs/standard/globalization-localization/globalization.md), y corrija los errores en el código fuente que impiden la localización.  
  
<a name="culture"></a>   
## Controlar características que tienen en cuenta la referencia cultural  
 .NET Framework no ofrece soporte técnico en varias áreas que varíen considerablemente según la referencia cultural.  En la mayoría de los casos, tiene que escribir código personalizado a las áreas de características ID como el siguiente:  
  
-   Direcciones.  
  
-   Números de teléfono.  
  
-   Tamaños de papel.  
  
-   Unidades de medida utilizadas para longitudes, las proporciones, área, el volumen, y las temperaturas.  Aunque .NET Framework no proporciona compatibilidad integrada para convertir entre unidades de medida, puede utilizar la propiedad de <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=fullName> para determinar si un país o región determinado utiliza el sistema métrica, como muestra el ejemplo siguiente.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## Probar la aplicación  
 Antes de buscar la aplicación, debe probarlo con datos internacionales en las versiones internacionales del sistema operativo.  Aunque la mayor parte de la interfaz de usuario no se encuentra en este punto, podrá detectar problemas como el siguiente:  
  
-   Datos serializados que no deserializar correctamente entre distintas versiones del sistema operativo.  
  
-   Tipo de datos numérico que no refleje las convenciones de la referencia cultural actual.  Por ejemplo, los números se pueden mostrar con los separadores de grupos, separadores decimales, o símbolos de moneda inexactos.  
  
-   Datos de fecha y hora que no refleje las convenciones de la referencia cultural actual.  Por ejemplo, los números que representan el mes y el día puede aparecer en el orden incorrecto, separadores de fecha pueden ser correctos, o la información de la zona horaria puede ser incorrecta.  
  
-   Recursos que no pueden encontrarse porque no ha identificado una referencia cultural predeterminada de la aplicación.  
  
-   Cadenas que se muestran en un orden inesperado para la referencia cultural específica.  
  
-   Comparaciones de cadenas o comparaciones de igualdad que devuelven resultados inesperados.  
  
 Si ha seguido las recomendaciones globalization al desarrollar la aplicación, características cultura\- confidenciales controlan correctamente, e identificar y resolver los problemas de localización que surgieron durante la prueba, puede continuar con el paso siguiente, [Localización](../../../docs/standard/globalization-localization/localization.md).  
  
## Vea también  
 [Globalización y localización](../../../docs/standard/globalization-localization/index.md)   
 [Localización](../../../docs/standard/globalization-localization/localization.md)   
 [Globalización](../../../docs/standard/globalization-localization/globalization.md)   
 [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md)