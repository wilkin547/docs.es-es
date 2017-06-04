---
title: "x:Shared Attribute | Microsoft Docs"
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
  - "XAML [XAML Services], x:Shared attribute"
  - "x:Shared attribute [XAML Services]"
  - "Shared attribute in XAML [XAML Services]"
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: 16
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 16
---
# x:Shared Attribute
Cuando se establece en `false`, modifica el comportamiento de recuperación de recursos de WPF, de forma que las solicitudes para un recurso de atributos crearán una nueva instancia por cada solicitud, en lugar de compartir la misma instancia para todas las solicitudes.  
  
## Uso de atributos XAML  
  
```  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## Comentarios  
 `x:Shared` está asignado en el espacio de nombres XAML de lenguaje XAML y se reconoce como un elemento de lenguaje XAML válido por servicios XAML de .NET Framework y sus lectores XAML.  Sin embargo, las capacidades comentadas de `x:Shared` únicamente son pertinentes en aplicaciones WPF y para el analizador XAML de WPF.  En WPF, `x:Shared` es útil únicamente como un atributo cuando se aplicó a un objeto que existe dentro de un WPF <xref:System.Windows.ResourceDictionary>.  Otros usos no producen excepciones de análisis ni otros errores, pero no tienen ningún efecto.  
  
 El significado de `x:Shared` no se especifica en la especificación de lenguaje XAML.  Otras implementaciones XAML, como aquellas que se compilan en servicios XAML de .NET Framework, no ofrecen necesariamente la compatibilidad de uso compartido de recursos.  Estas implementaciones XAML podrían proporcionar un comportamiento similar en el marco de apoyo que también utilizó los valores `x:Shared`.  
  
 En WPF, la condición de `x:Shared` predeterminada para los recursos es `true`.  Esta condición significa que cualquier solicitud de recurso devolverá siempre la misma instancia.  
  
 Al modificar un objeto devuelto a través de una API de recursos como <xref:System.Windows.FrameworkElement.FindResource%2A>, o al modificarlo directamente dentro de un <xref:System.Windows.ResourceDictionary>, se cambia el recurso original.  Si las referencias a ese recurso eran dinámicas, los consumidores de ese recurso obtienen el recurso modificado.  
  
 Si las referencias al recurso eran estáticas, los cambios que se produzcan en el recurso después del tiempo de procesamiento de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] serán irrelevantes.  Para obtener más información sobre las diferencias entre las referencias de recursos estáticas y dinámicas, consulte [Recursos XAML](../../../ocs/framework/wpf/advanced/xaml-resources.md).  
  
 No se suele especificar explícitamente `x:Shared="true"`, porque ya es el valor predeterminado.  No hay ningún código equivalente directo para `x:Shared` en el modelo de objeto de WPF; sólo se puede especificar en una utilización XAML y se debe procesar por el comportamiento de WPF predeterminado, o bien en una secuencia del nodo XAML intermedia de la ruta de acceso de carga si se procesa mediante los servicios XAML de .NET Framework y sus lectores XAML.  
  
 Un escenario para `x:Shared="false"` es aquel en que se define una clase derivada de <xref:System.Windows.FrameworkElement> o de <xref:System.Windows.FrameworkContentElement> como recurso y, a continuación, se introduce el recurso de elemento en un modelo de contenido.  `x:Shared="false"` permite introducir un recurso de elemento varias veces en la misma colección \(como <xref:System.Windows.Controls.UIElementCollection>, por ejemplo\).  Sin `x:Shared="false"` esto no es válido porque la colección exige la unicidad de su contenido.  Sin embargo, el comportamiento de `x:Shared="false"` crea otra instancia idéntica de recursos en lugar de devolver la misma instancia.  
  
 Otro escenario para `x:Shared="false"` es el uso de un recurso <xref:System.Windows.Freezable> para valores de animación, pero desea modificarlo para cada animación.  
  
 La administración de cadena de `false` no distingue mayúsculas de minúsculas.  
  
 En WPF, `x:Shared` únicamente es válido en las condiciones siguientes:  
  
-   El objeto <xref:System.Windows.ResourceDictionary> que contiene los elementos con `x:Shared` se debe compilar.  <xref:System.Windows.ResourceDictionary> no puede estar dentro de XAML dinámico ni se puede utilizar para temas.  
  
-   El objeto <xref:System.Windows.ResourceDictionary> que contiene los elementos no se puede anidar en otro <xref:System.Windows.ResourceDictionary>.  Por ejemplo, no puede utilizar `x:Shared` para los elementos de un objeto <xref:System.Windows.ResourceDictionary> que está dentro de un <xref:System.Windows.Style> que ya es un elemento de un <xref:System.Windows.ResourceDictionary>.  
  
## Vea también  
 <xref:System.Windows.ResourceDictionary>   
 [Recursos XAML](../../../ocs/framework/wpf/advanced/xaml-resources.md)   
 [Elementos base](../../../ocs/framework/wpf/advanced/base-elements.md)