---
title: "Seguridad de las propiedades de dependencia | Microsoft Docs"
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
  - "propiedades de dependencia, access"
  - "propiedades de dependencia, seguridad"
  - "seguridad, propiedades de dependencia"
  - "seguridad, contenedores"
  - "validación, propiedades de dependencia"
  - "contenedores, access"
  - "contenedores, seguridad"
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Seguridad de las propiedades de dependencia
Generalmente se debe considerar que las propiedades de dependencia son propiedades públicas.  La naturaleza del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] impide la capacidad de realizar garantías de seguridad sobre el valor de una propiedad de dependencia.  
  
   
  
<a name="AccessSecurity"></a>   
## Acceso y seguridad de contenedores y propiedades de a dependencia  
 Las propiedades de dependencia se suelen implementar junto con propiedades [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] "contenedor" que simplifican la obtención o el establecimiento de la propiedad desde una instancia.  Sin embargo, en realidad los contenedores no son más que métodos útiles que implementan las llamadas estáticas subyacentes a <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> utilizadas al interactuar con las propiedades de dependencia.  Expresado de otro modo, las propiedades se exponen como propiedades [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que resultan estar respaldadas por una propiedad de dependencia en lugar de por un campo privado.  Los mecanismos de seguridad aplicados a los contenedores no imitan el comportamiento ni el acceso del sistema de propiedades de la propiedad de dependencia subyacente.  Efectuar una petición de seguridad al contenedor únicamente impedirá el uso del método útil, pero no impedirá las llamadas a <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>.  De igual forma, poner un nivel de acceso protegido o privado en los contenedores tampoco proporciona ninguna seguridad efectiva.  
  
 Si escribe sus propias propiedades de dependencia, debe declarar los contenedores y el campo de identificador <xref:System.Windows.DependencyProperty> como miembros públicos, para que los llamadores no obtengan información engañosa sobre el verdadero nivel de acceso de esa propiedad \(por el hecho de que su almacén se implemente como una propiedad de dependencia\).  
  
 Para una propiedad de dependencia personalizada, puede registrar la propiedad como de dependencia y de sólo lectura, lo que sí proporciona un medio efectivo de evitar que establezca la propiedad cualquier persona que no posea una referencia a la <xref:System.Windows.DependencyPropertyKey> de esa propiedad.  Para obtener más información, vea [Propiedades de dependencia de sólo lectura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
> [!NOTE]
>  No se prohíbe declarar un campo de identificador <xref:System.Windows.DependencyProperty> privado. Resultaría plausible utilizarlo para contribuir a reducir el espacio de nombres inmediatamente expuesto de una clase personalizada, pero este tipo de propiedad no debe considerarse "privada" en el mismo sentido en que este nivel de acceso se define en las definiciones del lenguaje [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], por los motivos descritos en la sección siguiente.  
  
<a name="PropertySystemExposure"></a>   
## Exposición de sistema de propiedades de las propiedades de dependencia  
 En general, no resulta útil y puede dar lugar a confusión, declarar <xref:System.Windows.DependencyProperty> con cualquier nivel de acceso que no sea público.  Ese valor de nivel de acceso únicamente impedirá que una persona pueda obtener una referencia a la instancia desde la clase de declaración.  Sin embargo, hay varios aspectos del sistema de propiedades que devolverán una <xref:System.Windows.DependencyProperty> como manera de identificar una propiedad determinada tal como existe en una instancia de una clase o una instancia de clase derivada, y este identificador se puede utilizar en una llamada a <xref:System.Windows.DependencyObject.SetValue%2A> aunque el identificador estático original se haya declarado como no público.  Asimismo, los métodos virtuales <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> reciben información de cualquier propiedad de dependencia existente cuyo valor haya cambiado.  Además, el método <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> devuelve identificadores de cualquier propiedad para las instancias con un valor establecido localmente.  
  
### Validación y seguridad  
 Aplicar una petición a una propiedad <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> y esperar el error de validación si ésta no se cursa correctamente no es un mecanismo de seguridad adecuado para impedir que se establezca una propiedad.  Un llamador malintencionado que opere dentro del dominio de aplicación también puede suprimir la invalidación del establecimiento de valores mediante <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>.  
  
## Vea también  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)