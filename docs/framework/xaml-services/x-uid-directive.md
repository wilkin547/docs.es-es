---
title: "x:Uid Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XAML [XAML Services], localizable content attribute"
  - "XAML [XAML Services], x:Uid attribute"
  - "x:Uid attribute [XAML Services]"
  - "Uid attribute [XAML Services]"
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
caps.latest.revision: 12
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 12
---
# x:Uid Directive
Proporciona un identificador único para los elementos de marcado.  En muchos escenarios, los procesos y herramientas de localización de XAML usan este identificador único.  
  
## Uso de atributos XAML  
  
```  
<object x:Uid="identifier"... />  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`identifier`|Una cadena creada manualmente o generada de forma automática que debe ser única en un archivo cuando la interpreta un consumidor de `x:Uid`.|  
  
## Comentarios  
 En \[MS XAML\], `x:Uid` se define como una directiva.  Para obtener más información, vea [\[MS\-XAML\] sección 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` es discreto desde ambos `x:Name` debido al escenario de localización de XAML declarado y para que los identificadores utilizados para la localización no tengan ninguna dependencia en las implicaciones del modelo de programación de `x:Name`.  Además, `x:Name` se rige por el ámbito de nombres XAML; sin embargo, `x:Uid` no se rige por ningún concepto definido del lenguaje XAML de cumplimiento de singularidad.  No se espera que los procesadores XAML en sentido amplio \(aquellos que no forman parte necesariamente del proceso de localización\) exijan que los valores de `x:Uid` sean únicos.  Esa responsabilidad se encuentra conceptualmente en el originador de los valores.  La expectativa de singularidad de los valores `x:Uid` con un único origen XAML es razonable para los consumidores de los valores, tales como los procesos o las herramientas de globalización dedicados.  El modelo de singularidad típico es que los valores `x:Uid` son únicos dentro de un archivo codificado XML que representa XAML.  
  
 Las herramientas con un conocimiento significativo de un esquema XAML determinado podrían optar por aplicar `x:Uid` solo en verdaderas cadenas traducibles, en lugar de en todos los casos donde un valor de cadena de texto se encuentra en el marcado.  
  
 .NET Framework puede especificar una propiedad determinada en su modelo de objetos para ser un alias para `x:Uid` aplicando el atributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo de definición.  Si un marco especifica una propiedad determinada, no es válido especificar `x:Uid` y el miembro con alias en el mismo objeto.  Si especifica `x:Uid` y el miembro con alias, la API de los servicios XAML de .NET Framework producen normalmente <xref:System.Xaml.XamlDuplicateMemberException> para este caso.  
  
## Notas de uso de WPF  
 Para obtener más información acerca del rol de `x:Uid` en el proceso de localización de WPF y en el formulario BAML de XAML, vea [Globalización de WPF](../../../ocs/framework/wpf/advanced/globalization-for-wpf.md) o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## Vea también  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>   
 <xref:Microsoft.Build.Tasks.Windows.UidManager>   
 [Globalización de WPF](../../../ocs/framework/wpf/advanced/globalization-for-wpf.md)