---
title: Cómo registrar y configurar un moniker de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: fc0b2d00bcc8e3b14c491446f16297c1036b783b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747096"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a>Cómo registrar y configurar un moniker de servicio

Antes de utilizar el moniker del servicio Windows Communication Foundation (WCF) dentro de una aplicación COM con un contrato con tipo, debe registrar los tipos con atributos necesarios en COM y configurar la aplicación COM y el moniker con el enlace necesario configuraciones.

## <a name="register-the-required-attributed-types-with-com"></a>Registrar los tipos con atributos necesarios con COM

1. Use la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para recuperar el contrato de metadatos del servicio WCF. Esto genera el código fuente para un ensamblado de cliente de WCF y un archivo de configuración de la aplicación cliente.

2. Asegúrese de que los tipos del ensamblado se marcan como `ComVisible`. Para ello, agregue el siguiente atributo al archivo *AssemblyInfo.CS* en el proyecto de Visual Studio.

    ```csharp
    [assembly: ComVisible(true)]
    ```

3. Compile el cliente WCF administrado como un ensamblado con nombre seguro. Para ello se es necesario firmar con un par de claves criptográficas. Para obtener más información, vea [Signing an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md) (Firmar un ensamblado con un nombre seguro).

4. Utilice la herramienta de registro de ensamblados (Regasm.exe) con la opción `-tlb` para registrar los tipos del ensamblado en COM.

5. Use la herramienta de la caché global de ensamblados (Gacutil.exe) para agregar el ensamblado a la caché global de ensamblados.

    > [!NOTE]
    > Firmar y agregar el ensamblado a la caché global de ensamblados son pasos opcionales, pero permiten simplificar el proceso de carga del ensamblado desde la ubicación correcta en el tiempo de ejecución.

## <a name="configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a>Configurar la aplicación COM y el moniker con la configuración de enlace necesaria

- Coloque las definiciones de enlace (generadas por la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) en el archivo de configuración de la aplicación cliente generada) en el archivo de configuración de la aplicación cliente. Por ejemplo, para un ejecutable de Visual Basic 6.0 denominado CallCenterClient.exe, la configuración debe encontrarse en un archivo denominado CallCenterConfig.exe.config en el mismo directorio que la aplicación ejecutable. De este modo la aplicación cliente puede utilizar el moniker. Tenga en cuenta que la configuración de enlace no es necesaria si se usa uno de los tipos de enlace estándar que proporciona WCF.

     El siguiente tipo está registrado:

    ```csharp
    using System.ServiceModel;

    [ServiceContract]
    public interface IMathService
    {
        [OperationContract]
        public int Add(int x, int y);
        [OperationContract]
        public int Subtract(int x, int y);
    }
    ```

     La aplicación se expone mediante un enlace `wsHttpBinding`. Para el tipo y configuración de aplicación especificados, se utilizan las siguientes cadenas moniker de ejemplo.

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1
    ```

     o

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}
    ```

     Puede utilizar cualquiera de estas cadenas moniker desde una aplicación de Visual Basic 6.0, siempre que agregue una referencia al ensamblado que contiene los tipos `IMathService`, como se muestra en el siguiente código de ejemplo.

    ```vb
    Dim mathProxy As IMathService
    Dim result As Integer

    Set mathProxy = GetObject( _
            "service4:address=http://localhost/MathService, _
            binding=wsHttpBinding, _
            bindingConfiguration=Binding1")

    result = mathProxy.Add(3, 5)
    ```

     En este ejemplo, la definición del `Binding1` de configuración de enlace se almacena en un archivo de configuración con un nombre adecuado para la aplicación cliente, como *vb6appname. exe. config*.

    > [!NOTE]
    > Puede utilizar un código similar en una aplicación C#, C++, o cualquier otra aplicación de lenguaje .NET.

    > [!NOTE]
    > Si el moniker tiene un formato incorrecto o si el servicio no está disponible, la llamada a `GetObject` devuelve un error de "sintaxis no válida". Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.

     Aunque este tema se centra en el uso del moniker de servicio de Visual Basic Código 6,0, se puede utilizar un moniker de servicio de otros lenguajes. Si utiliza un moniker del código de C++, deberá importar el ensamblado generado por Svcutil.exe con "no_namespace named_guids raw_interfaces_only", como se muestra en el siguiente código.

    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids
    ```

     De este modo se modifican las definiciones de la interfaz importada para que todos los métodos devuelvan `HResult`. Cualquier otro valor devuelto se convierte en parámetros de salida. La ejecución global de los métodos sigue siendo la misma. Esto permite determinar la causa de una excepción al llamar a un método en el proxy. Esta funcionalidad sólo está disponible en el código de C++.

## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
