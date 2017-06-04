---
title: "Cifrado de firmas digitales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "firmas digitales [WCF]"
  - "firmas digitales [WCF], cifrado"
  - "cifrado de firmas digitales [WCF]"
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Cifrado de firmas digitales
De forma predeterminada, un mensaje se cifra y se firma y la firma se cifra digitalmente.Puede controlar esto creando un enlace personalizado con una instancia de <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y estableciendo la propiedad `MessageProtectionOrder` de cualquier clase en un valor de enumeración <xref:System.ServiceModel.Security.MessageProtectionOrder>.El valor predeterminado es <xref:System.ServiceModel.Security.MessageProtectionOrder>.Este proceso tarda entre un 10 y un 40 por ciento más que la simple firma y cifrado.Deshabilitar el cifrado de la firma, sin embargo, puede permitir a un atacante adivinar el contenido del mensaje.Esto es posible porque el elemento de firma contiene el código hash del texto sin formato de cada parte firmada en el mensaje.Por ejemplo, aunque se cifra el cuerpo del mensaje de forma predeterminada, la firma no cifrada contiene el código hash del cuerpo del mensaje.Si el mensaje es pequeño, un atacante podría ser capaz de deducir el contenido.Cifrar la firma reduce o elimina esta posibilidad.  
  
 Por consiguiente, solo deshabilite el cifrado de la firma cuando el valor del contenido sea bajo y el aumento de rendimiento significativo, por ejemplo, al enviar archivos binarios de gran tamaño que no tienen implicaciones de seguridad.  
  
### Para deshabilitar la firma digital  
  
1.  Cree un objeto <xref:System.ServiceModel.Channels.CustomBinding>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2.  Agregue <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> a la colección de enlaces.  
  
3.  Defina la propiedad <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> en <xref:System.ServiceModel.Security.MessageProtectionOrder> o defina la propiedad <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> en <xref:System.ServiceModel.Security.MessageProtectionOrder>.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo crear enlaces predeterminados, vea [Creación de enlaces definidos por el usuario](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo crear un enlace predeterminado para un modo de autenticación concreto, vea [Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## Vea también  
 <xref:System.ServiceModel.Security.MessageProtectionOrder>   
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Creación de enlaces definidos por el usuario](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)   
 [Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)