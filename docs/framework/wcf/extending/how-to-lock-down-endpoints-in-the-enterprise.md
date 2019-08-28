---
title: Procedimiento para bloquear puntos de conexión en la empresa
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: d2a0299dd67e6efe3e3d9e6bae81265d4ad314ee
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040277"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Procedimiento para bloquear puntos de conexión en la empresa

Las grandes empresas requieren a menudo que las aplicaciones se desarrollen conforme a las directivas de seguridad de la empresa. En el siguiente tema se describe cómo desarrollar e instalar un validador de punto de conexión de cliente que se puede utilizar para validar todas las aplicaciones cliente de Windows Communication Foundation (WCF) instaladas en los equipos.

En este caso, el validador es un validador de cliente porque este comportamiento de extremo se agrega a la sección Client [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) del archivo Machine. config. WCF carga los comportamientos de extremo comunes solo para las aplicaciones cliente y carga los comportamientos de servicio comunes solo para las aplicaciones de servicio. Para instalar el mismo validador para las aplicaciones servicio, el validador debe ser un comportamiento de servicio. Para obtener más información, consulte la [ \<sección commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) .

> [!IMPORTANT]
> Los comportamientos de servicio o de extremo que <xref:System.Security.AllowPartiallyTrustedCallersAttribute> no están marcados con el atributo (APTCA) que se agregan a la [ \<sección > de commonBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) de un archivo de configuración no se ejecutan cuando la aplicación se ejecuta en un entorno de confianza parcial, y no Cuando esto ocurre, se produce una excepción. Para forzar la ejecución de los comportamientos habituales, como los validadores, es necesario:
>
> - Marque el comportamiento común con el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo para que pueda ejecutarse cuando se implemente como una aplicación de confianza parcial. Tenga en cuenta que puede establecerse una entrada de registro en el equipo para evitar que se ejecuten los ensamblados marcados con APTCA.
>
> - Asegúrese de que si la aplicación se implementa como una aplicación de plena confianza que los usuarios no pueden modificar la configuración de seguridad de acceso del código para ejecutar la aplicación en un entorno de confianza parcial. De poder hacerlo, el validador personalizado no se ejecutaría y no se iniciaría ninguna excepción. Para obtener una manera de asegurarse de esto, `levelfinal` vea la opción usar la herramienta de la [Directiva de seguridad de acceso del código (Caspol. exe)](https://go.microsoft.com/fwlink/?LinkId=248222).
>
> Para obtener más información, consulte [procedimientos recomendados de confianza parcial](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) y [escenarios de implementación admitidos](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).

### <a name="to-create-the-endpoint-validator"></a>Para crear el validador de punto de conexión

1. Cree un <xref:System.ServiceModel.Description.IEndpointBehavior> con los pasos de validación que desee en el método <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>. El siguiente código proporciona un ejemplo. (El `InternetClientValidatorBehavior` se toma del ejemplo de [validación de seguridad](../../../../docs/framework/wcf/samples/security-validation.md) ).

    [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]

2. Cree un nuevo <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> que registre el validador de punto de conexión creado en el paso 1. El ejemplo de código siguiente muestra cómo hacerlo. (El código original de este ejemplo está en el ejemplo de [validación de seguridad](../../../../docs/framework/wcf/samples/security-validation.md) ).

    [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]

3. Asegúrese de que el ensamblado compilado se firma con un nombre seguro. Para obtener más información, consulte la [herramienta de nombre seguro (SN). EXE)](https://go.microsoft.com/fwlink/?LinkId=248217) y los comandos del compilador para su lenguaje.

### <a name="to-install-the-validator-into-the-target-computer"></a>Para instalar el validador en el equipo de destino

1. Instale el validador del punto de conexión mediante el mecanismo adecuado. En una empresa, esto puede hacerse utilizando la directiva de grupo y Systems Management Server (SMS).

2. Instale el ensamblado con nombre seguro en la caché global de ensamblados con [Gacutil. exe (herramienta de caché global de ensamblados)](../../../../docs/framework/tools/gacutil-exe-gac-tool.md).

3. Utilice los tipos de espacio de nombres de <xref:System.Configuration?displayProperty=nameWithType> para:

    1. Agregue la extensión a la [ \<sección > de behaviorExtensions](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) con un nombre de tipo completo y bloquee el elemento.

         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]

    2. Agregue el elemento de comportamiento a `EndpointBehaviors` la propiedad de la [ \<sección commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) y bloquee el elemento. (Para instalar el validador en el servicio, el validador debe ser un <xref:System.ServiceModel.Description.IServiceBehavior> que se agregue a la propiedad `ServiceBehaviors`.) El ejemplo de código siguiente se muestra la configuración adecuada después de los pasos a. y b., con la única excepción de que no hay ningún nombre seguro.

        [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]

    3. Guarde el archivo machine.config. El ejemplo de código siguiente realiza todas las tareas en el paso 3 pero guarda localmente una copia del archivo machine.config modificado.

        [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra cómo agregar un comportamiento común al archivo machine.config y guardar una copia en el disco. El `InternetClientValidatorBehavior` se toma del ejemplo de [validación de seguridad](../../../../docs/framework/wcf/samples/security-validation.md) .

[!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]

## <a name="net-framework-security"></a>Seguridad de .NET Framework

También puede querer cifrar los elementos del archivo de configuración. Para obtener más información, vea la sección Vea también.

## <a name="see-also"></a>Vea también

- [Cifrar los elementos del archivo de configuración mediante DPAPI](https://go.microsoft.com/fwlink/?LinkId=94954)
- [Cifrar los elementos del archivo de configuración mediante RSA](https://go.microsoft.com/fwlink/?LinkId=94955)
