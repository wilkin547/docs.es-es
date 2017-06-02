---
title: "C&#243;mo restringir el acceso con la clase PrincipalPermissionAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Clase PrincipalPermissionAttribute"
  - "WCF, autorización"
  - "WCF, seguridad"
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# C&#243;mo restringir el acceso con la clase PrincipalPermissionAttribute
Controlar el acceso a los recursos en un equipo del dominio de Windows es una tarea de seguridad básica.Por ejemplo, solo ciertos usuarios deberían poder ver los datos confidenciales, como la información de la nómina.Este tema explica cómo restringir el acceso a un método exigiendo que el usuario pertenezca a un grupo predefinido.Para ver un ejemplo práctico, consulte [Autorización de acceso a operaciones de servicio](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).  
  
 La tarea está compuesta de dos procedimientos independientes.El primero crea el grupo y lo rellena con usuarios.El segundo aplica la clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> para especificar el grupo.  
  
### Para crear un grupo de Windows  
  
1.  Abra la consola **Administración del equipo**.  
  
2.  En el panel izquierdo, haga clic en **Usuarios y grupos locales**.  
  
3.  Haga clic con el botón secundario en **Grupos**y haga clic en **Nuevo grupo**.  
  
4.  En la casilla **Nombre de grupo**, escriba un nombre para el nuevo grupo.  
  
5.  En la casilla **Descripción**, escriba una descripción del nuevo grupo.  
  
6.  Para agregar nuevos miembros al grupo, haga clic en **Agregar**.  
  
7.  Si se ha agregado al grupo y desea probar el código siguiente, debe cerrar la sesión en el equipo y volver a iniciarla para estar incluido en el grupo.  
  
### Para exigir la pertenencia del usuario  
  
1.  Abra el archivo de código de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] que contiene el código de contrato de servicio implementado.[!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo implementar un contrato, vea [Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
2.  Aplique el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a cada método que debe estar restringido a un grupo concreto.Establezca la propiedad <xref:System.Security.Permissions.SecurityAttribute.Action%2A> en <xref:System.Security.Permissions.SecurityAction> y la propiedad <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> en el nombre del grupo.Por ejemplo:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  Si se aplica el atributo a un contrato <xref:System.Security.Permissions.PrincipalPermissionAttribute>, se iniciará una <xref:System.Security.SecurityException>.El atributo solo puede aplicarse en el nivel del método.  
  
## Uso de un certificado para controlar el acceso a un método  
 También puede utilizar la clase `PrincipalPermissionAttribute` para controlar el acceso a un método si el tipo de credencial de cliente es un certificado.Para hacerlo, debe tener el asunto y la huella digital del certificado.  
  
 Para examinar las propiedades de un certificado, vea [Cómo: Ver certificados con el complemento de MMC](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).Para encontrar el valor de huella digital, vea [Cómo recuperar la huella digital de un certificado](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
#### Para controlar el acceso mediante un certificado  
  
1.  Aplique la clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> al método al que desea restringir el acceso.  
  
2.  Establezca la acción del atributo en <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>.  
  
3.  Establezca la propiedad `Name` en una cadena que esté compuesta del nombre del sujeto y la huella digital del certificado.Separe los dos valores con un punto y coma y un espacio, como se muestra en el ejemplo siguiente:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4.  Establezca la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> en <xref:System.ServiceModel.Description.PrincipalPermissionMode> como se muestra en el siguiente ejemplo de configuración:  
  
    ```  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     Establecer este valor en `UseAspNetRoles` indica que la propiedad `Name` del `PrincipalPermissionAttribute` se utilizará para realizar una comparación de cadenas.Cuando se utiliza un certificado como una credencial del cliente, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] concatena de forma predeterminada el nombre común del certificado y la huella digital con un punto y coma para crear un valor único para la identidad primaria del cliente.Con `UseAspNetRoles` establecido como `PrincipalPermissionMode` en el servicio, este valor de identidad primaria se compara con el valor de la propiedad `Name` para determinar los derechos de acceso del usuario.  
  
     Alternativamente, al crear un servicio autohospedado, establezca la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> en código como se muestra en el código siguiente:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## Vea también  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>   
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>   
 <xref:System.Security.Permissions.SecurityAction>   
 <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>   
 [Autorización de acceso a operaciones de servicio](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [Información general sobre seguridad](../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md)