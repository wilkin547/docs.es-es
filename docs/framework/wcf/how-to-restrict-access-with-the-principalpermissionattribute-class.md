---
description: 'Más información acerca de cómo: restringir el acceso con la clase PrincipalPermissionAttribute'
title: Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
ms.openlocfilehash: 533bd3358d5e337071c6419264d1dac03b8987ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779353"
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a>Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute

Controlar el acceso a los recursos en un equipo del dominio de Windows es una tarea de seguridad básica. Por ejemplo, solo ciertos usuarios deberían poder ver los datos confidenciales, como la información de la nómina. Este tema explica cómo restringir el acceso a un método exigiendo que el usuario pertenezca a un grupo predefinido. Para obtener un ejemplo de trabajo, vea el apartado sobre cómo [autorizar el acceso a las operaciones de servicio](./samples/authorizing-access-to-service-operations.md).  
  
 La tarea está compuesta de dos procedimientos independientes. El primero crea el grupo y lo rellena con usuarios. El segundo aplica la clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> para especificar el grupo.  
  
### <a name="to-create-a-windows-group"></a>Para crear un grupo de Windows  
  
1. Abra la consola de **Administración de equipos** .  
  
2. En el panel izquierdo, haga clic en **usuarios y grupos locales**.  
  
3. Haga clic con el botón secundario en **grupos** y haga clic en **nuevo grupo**.  
  
4. En el cuadro **nombre de grupo** , escriba un nombre para el nuevo grupo.  
  
5. En el cuadro **Descripción** , escriba una descripción del nuevo grupo.  
  
6. Haga clic en el botón **Agregar** para agregar nuevos miembros al grupo.  
  
7. Si se ha agregado al grupo y desea probar el código siguiente, debe cerrar la sesión en el equipo y volver a iniciarla para estar incluido en el grupo.  
  
### <a name="to-demand-user-membership"></a>Para exigir la pertenencia del usuario  
  
1. Abra el archivo de código Windows Communication Foundation (WCF) que contiene el código de contrato de servicio implementado. Para obtener más información sobre la implementación de un contrato, consulte [implementación de contratos de servicio](implementing-service-contracts.md).  
  
2. Aplique el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a cada método que debe estar restringido a un grupo concreto. Establezca la propiedad <xref:System.Security.Permissions.SecurityAttribute.Action%2A> en <xref:System.Security.Permissions.SecurityAction.Demand> y la propiedad <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> en el nombre del grupo. Por ejemplo:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    > Si se aplica el atributo a un contrato <xref:System.Security.Permissions.PrincipalPermissionAttribute>, se iniciará una <xref:System.Security.SecurityException>. El atributo solo puede aplicarse en el nivel del método.  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a>Uso de un certificado para controlar el acceso a un método  

 También puede utilizar la clase `PrincipalPermissionAttribute` para controlar el acceso a un método si el tipo de credencial de cliente es un certificado. Para hacerlo, debe tener el asunto y la huella digital del certificado.  
  
 Para examinar un certificado para sus propiedades, consulte [Cómo: ver certificados con el complemento MMC](./feature-details/how-to-view-certificates-with-the-mmc-snap-in.md). Para buscar el valor de huella digital, consulte [Cómo: recuperar la huella digital de un certificado](./feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
#### <a name="to-control-access-using-a-certificate"></a>Para controlar el acceso mediante un certificado  
  
1. Aplique la clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> al método al que desea restringir el acceso.  
  
2. Establezca la acción del atributo en <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.  
  
3. Establezca la propiedad `Name` en una cadena que esté compuesta del nombre del sujeto y la huella digital del certificado. Separe los dos valores con un punto y coma y un espacio, como se muestra en el ejemplo siguiente:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4. Establezca la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> en <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> como se muestra en el siguiente ejemplo de configuración:  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     Establecer este valor en `UseAspNetRoles` indica que la propiedad `Name` del `PrincipalPermissionAttribute` se utilizará para realizar una comparación de cadenas. Cuando se usa un certificado como credencial de cliente, WCF concatena de forma predeterminada el nombre común del certificado y la huella digital con un punto y coma para crear un valor único para la identidad principal del cliente. Con `UseAspNetRoles` establecido como `PrincipalPermissionMode` en el servicio, este valor de identidad primaria se compara con el valor de la propiedad `Name` para determinar los derechos de acceso del usuario.  
  
     Alternativamente, al crear un servicio autohospedado, establezca la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> en código como se muestra en el código siguiente:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- <xref:System.Security.Permissions.SecurityAction.Demand>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>
- [Autorización de acceso a operaciones de servicio](./samples/authorizing-access-to-service-operations.md)
- [Información general sobre seguridad](./feature-details/security-overview.md)
- [Implementación de contratos de servicio](implementing-service-contracts.md)
