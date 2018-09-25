---
title: Cómo bloquear puntos de conexión en la empresa
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: 032b69c1fae38576b0374b329f1ab6fe90e2b1a0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075529"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Cómo bloquear puntos de conexión en la empresa
Las grandes empresas requieren a menudo que las aplicaciones se desarrollen conforme a las directivas de seguridad de la empresa. El siguiente tema describe cómo desarrollar e instalar un validador de punto de conexión de cliente que puede usarse para validar todas las aplicaciones cliente de Windows Communication Foundation (WCF) instaladas en los equipos.  
  
 En este caso, el validador es un validador de cliente porque este comportamiento de punto de conexión se agrega al cliente [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) sección en el archivo machine.config. WCF carga los comportamientos de extremo comunes solo para las aplicaciones cliente y carga los comportamientos de servicio comunes solo para aplicaciones de servicio. Para instalar el mismo validador para las aplicaciones servicio, el validador debe ser un comportamiento de servicio. Para obtener más información, consulte el [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) sección.  
  
> [!IMPORTANT]
>  Comportamientos de servicio o punto de conexión no están marcados con el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo (APTCA) que se agregan a la [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) sección de un archivo de configuración no se ejecutan cuando la aplicación se ejecuta en una relación de confianza parcial entorno y ninguna excepción se produce cuando ocurre esto. Para forzar la ejecución de los comportamientos habituales, como los validadores, es necesario:  
>   
>  -- Marcar el comportamiento habitual con el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> de modo que pueda ejecutarse cuando se implementa como una aplicación de confianza parcial. Tenga en cuenta que puede establecerse una entrada de registro en el equipo para evitar que se ejecuten los ensamblados marcados con APTCA.  
>   
>  -- Asegurarse de implementar la aplicación como una aplicación de confianza total en la que los usuarios no pueden modificar los valores de la seguridad de acceso del código para ejecutar la aplicación en un entorno de confianza parcial. De poder hacerlo, el validador personalizado no se ejecutaría y no se iniciaría ninguna excepción. Para que una forma de asegurarse de esto, consulte el `levelfinal` mediante la opción [Code Access Security Policy Tool (Caspol.exe)](https://go.microsoft.com/fwlink/?LinkId=248222).  
>   
>  Para obtener más información, consulte [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) y [admite escenarios de implementación](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
### <a name="to-create-the-endpoint-validator"></a>Para crear el validador de punto de conexión  
  
1.  Cree un <xref:System.ServiceModel.Description.IEndpointBehavior> con los pasos de validación que desee en el método <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>. El siguiente código proporciona un ejemplo. (El `InternetClientValidatorBehavior` procede de la [validación de seguridad](../../../../docs/framework/wcf/samples/security-validation.md) ejemplo.)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  Cree un nuevo <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> que registre el validador de extremo creado en el paso 1. El ejemplo de código siguiente muestra cómo hacerlo. (El código original para este ejemplo está en el [validación de seguridad](../../../../docs/framework/wcf/samples/security-validation.md) ejemplo.)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  Asegúrese de que el ensamblado compilado se firma con un nombre seguro. Para obtener más información, consulte el [Strong Name Tool (SN. (EXE)](https://go.microsoft.com/fwlink/?LinkId=248217) y los comandos del compilador para su idioma.  
  
### <a name="to-install-the-validator-into-the-target-computer"></a>Para instalar el validador en el equipo de destino  
  
1.  Instale el validador del extremo mediante el mecanismo adecuado. En una empresa, esto puede hacerse utilizando la directiva de grupo y Systems Management Server (SMS).  
  
2.  Instalar el ensamblado con nombre seguro en la caché global de ensamblados mediante la [Gacutil.exe (Global Assembly Cache Tool)](https://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx).  
  
3.  Utilice los tipos de espacio de nombres de <xref:System.Configuration?displayProperty=nameWithType> para:  
  
    1.  Agregue la extensión a la [ \<behaviorExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) sección con un nombre de tipo completo y bloquee el elemento.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  Agregue el elemento de comportamiento a la `EndpointBehaviors` propiedad de la [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) sección y bloquee el elemento. (Para instalar el validador en el servicio, el validador debe ser un <xref:System.ServiceModel.Description.IServiceBehavior> que se agregue a la propiedad `ServiceBehaviors`.) El ejemplo de código siguiente se muestra la configuración adecuada después de los pasos a. y b., con la única excepción de que no hay ningún nombre seguro.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  Guarde el archivo machine.config. El ejemplo de código siguiente realiza todas las tareas en el paso 3 pero guarda localmente una copia del archivo machine.config modificado.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo agregar un comportamiento común al archivo machine.config y guardar una copia en el disco. El `InternetClientValidatorBehavior` procede de la [validación de seguridad](../../../../docs/framework/wcf/samples/security-validation.md) ejemplo.  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 También puede querer cifrar los elementos del archivo de configuración. Para obtener más información, vea la sección Vea también.  
  
## <a name="see-also"></a>Vea también  
 [Cifrar los elementos del archivo de configuración mediante DPAPI](https://go.microsoft.com/fwlink/?LinkId=94954)  
 [Cifrar los elementos de archivo de configuración con RSA](https://go.microsoft.com/fwlink/?LinkId=94955)
