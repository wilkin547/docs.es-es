---
title: Serialización de interoperabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
ms.openlocfilehash: 70514811a9d236dc485f64fc34297cdb057a1512
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124276"
---
# <a name="interop-marshaling"></a>Serialización de interoperabilidad

La serialización de interoperabilidad rige cómo se pasan los datos en argumentos de método y valores devueltos entre la memoria administrada y la no administrada durante las llamadas. La serialización de interoperabilidad es una actividad en tiempo de ejecución realizada por el servicio de serialización de Common Language Runtime.

La mayoría de los tipos de datos tienen representaciones comunes tanto en la memoria administrada como en la no administrada. El administrador de serialización de interoperabilidad controla esos tipos automáticamente. El resto de tipos pueden ser ambiguos o no estar representados en la memoria administrada.

Un tipo ambiguo puede tener varias representaciones no administradas que se asignan a un solo tipo administrado, o bien no tener información de tipos, como el tamaño de una matriz. Para los tipos ambiguos, el administrador de serialización proporciona una representación predeterminada y varias representaciones alternativas si existen. Se pueden proporcionar instrucciones explícitas al administrador de serialización sobre cómo serializar un tipo ambiguo.

## <a name="platform-invoke-and-com-interop-models"></a>Modelos de invocación de plataforma e interoperabilidad COM

Common Language Runtime proporciona dos mecanismos para interoperar con código no administrado:

- Invocación de plataforma, que permite al código administrado llamar a funciones exportadas desde una biblioteca no administrada.
- Interoperabilidad COM, que permite al código administrado interactuar con modelos de objetos componentes (COM) a través de interfaces.

Tanto la invocación de plataforma como la interoperabilidad COM usan serialización de interoperabilidad para mover con precisión los argumentos de método desde el llamador al destinatario y viceversa, si es necesario. Como se muestra en la siguiente ilustración, una llamada al método de invocación de plataforma fluye desde el código administrado al no administrado y nunca en sentido contrario, excepto cuando hay [funciones de devolución de llamada](callback-functions.md) implicadas. Aunque las llamadas de invocación de plataforma solo pueden realizarse desde código administrado a código no administrado, los datos pueden fluir en ambas direcciones como parámetros de entrada o salida. Las llamadas a métodos de interoperabilidad COM pueden fluir en ambas direcciones.

![Invocación de plataforma](./media/interop-marshaling/interop-marshaling-invoke-and-com.png "Flujo de llamadas de invocación de plataforma e interoperabilidad COM")

En el nivel más bajo, ambos mecanismos usan el mismo servicio de serialización de interoperabilidad; sin embargo, hay determinados tipos de datos que solo se admiten en la interoperabilidad COM o en la invocación de plataforma. Para obtener más información, vea [Comportamiento de serialización predeterminado](default-marshaling-behavior.md).

## <a name="marshaling-and-com-apartments"></a>Serialización y apartamentos COM

El administrador de serialización de interoperabilidad serializa datos entre el montón de Common Language Runtime y el montón no administrado. La serialización se produce siempre que el llamador y el destinatario no pueden operar en la misma instancia de datos. El administrador de serialización de interoperabilidad permite al llamador y al destinatario operar en los mismos datos, incluso aunque tengan su propia copia de los datos.

COM también dispone de un administrador de serialización que serializa datos entre apartamentos COM o diferentes procesos COM. Al realizar llamadas entre código administrado y no administrado en el mismo apartamento COM, el administrador de serialización de interoperabilidad es el único administrador de serialización implicado. Al realizar llamadas entre código administrado y código no administrado en un apartamento COM diferente o en un proceso diferente, están implicados tanto el administrador de serialización de interoperabilidad como el administrador de serialización de COM.

### <a name="com-clients-and-managed-servers"></a>Clientes COM y servidores administrados

Un servidor administrado exportado con una biblioteca de tipos registrada por la [herramienta de registro de ensamblados (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) tiene una entrada del Registro `ThreadingModel` establecida en `Both`. Este valor indica que el servidor puede activarse en un contenedor uniproceso (STA) o en un contenedor multiproceso (MTA). El objeto de servidor se crea en el mismo apartamento que su llamador, como se muestra en la siguiente tabla:

|Cliente COM|Servidor .NET|Requisitos de serialización|
|----------------|-----------------|-----------------------------|
|STA|`Both` se convierte en STA.|Serialización en mismo apartamento.|
|MTA|`Both` se convierte en MTA.|Serialización en mismo apartamento.|

Dado que el cliente y el servidor están en el mismo apartamento, el servicio de serialización de interoperabilidad controla automáticamente toda la serialización de datos. La ilustración siguiente muestra cómo opera el servicio de serialización de interoperabilidad entre montones administrados y no administrados dentro del mismo apartamento de estilo COM.

![Serialización de la interoperabilidad entre montones administrados y no administrados](./media/interop-marshaling/interop-heaps-managed-and-unmanaged.gif "Proceso de serialización en el mismo apartamento")

Si planea exportar un servidor administrado, tenga en cuenta que el cliente COM determina el apartamento del servidor. Un servidor administrado llamado por un cliente COM inicializado en un MTA debe garantizar la seguridad de subprocesos.

### <a name="managed-clients-and-com-servers"></a>Clientes administrados y servidores COM

La configuración predeterminada para apartamentos de cliente administrado es MTA; sin embargo, el tipo de aplicación del cliente .NET puede cambiar la configuración predeterminada. Por ejemplo, una configuración de apartamento cliente de Visual Basic es STA. Puede usar <xref:System.STAThreadAttribute?displayProperty=nameWithType>, <xref:System.MTAThreadAttribute?displayProperty=nameWithType>, la propiedad <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> o la propiedad <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> para examinar y cambiar la configuración de apartamento de un cliente administrado.

El autor del componente establece la afinidad del subproceso de un servidor COM. En la tabla siguiente se muestran las combinaciones de configuraciones de apartamentos para clientes .NET y servidores COM. También se muestran los requisitos de serialización resultantes para las combinaciones.

|Cliente .NET|Servidor COM|Requisitos de serialización|
|-----------------|----------------|-----------------------------|
|MTA (valor predeterminado)|MTA<br /><br /> STA|Serialización de interoperabilidad.<br /><br /> Serialización de interoperabilidad y COM.|
|STA|MTA<br /><br /> STA|Serialización de interoperabilidad y COM.<br /><br /> Serialización de interoperabilidad.|

Cuando un cliente administrado y un servidor no administrado están en el mismo apartamento, el servicio de serialización de interoperabilidad controla toda la serialización de datos. Sin embargo, cuando el cliente y el servidor se inicializan en apartamentos diferentes, también es necesaria la serialización de COM. En la siguiente ilustración se muestran los elementos de una llamada entre apartamentos:

![Serialización COM](./media/interop-marshaling/single-process-across-multi-apartment.gif "Llamada entre apartamentos entre un cliente .NET y un objeto COM")

Para una serialización entre apartamentos, puede hacer lo siguiente:

- Aceptar la sobrecarga que supone la serialización entre apartamentos, que solo es apreciable cuando hay muchas llamadas que cruzan el límite. Debe registrar la biblioteca de tipos del componente COM para que las llamadas crucen correctamente el límite del apartamento.
- Establecer el subproceso de cliente en STA o MTA para alterar el subproceso principal. Por ejemplo, si el cliente de C# llama a muchos componentes COM de STA, puede evitar la serialización entre apartamentos si establece el subproceso principal en STA.

    > [!NOTE]
    > Una vez que se establece el subproceso de un cliente C# en STA, las llamadas a componentes COM de MTA requerirán la serialización entre apartamentos.

Para obtener instrucciones sobre cómo seleccionar explícitamente un modelo de contenedor, vea [Subprocesamiento administrado y no administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100)).

## <a name="marshaling-remote-calls"></a>Serialización de llamadas remotas

Al igual que con la serialización entre apartamentos, la serialización de COM participa en todas las llamadas entre código administrado y no administrado siempre que los objetos residan en procesos independientes. Por ejemplo:

- Un cliente COM que invoca a un servidor administrado en un host remoto usa COM distribuido (DCOM).
- Un cliente administrado que invoca a un servidor COM en un host remoto usa DCOM.

En la siguiente ilustración se muestra cómo la serialización de interoperabilidad y la serialización de COM proporcionan canales de comunicación a través de procesos y límites de hosts:

![Serialización COM](./media/interop-marshaling/interop-and-com-marshaling.gif "Serialización entre procesos")

### <a name="preserving-identity"></a>Conservar la identidad

Common Language Runtime conserva la identidad de las referencias administradas y no administradas. En la siguiente ilustración se muestra el flujo de referencias directas no administradas (fila superior) y de referencias directas administradas (fila inferior) entre procesos y límites de hosts.

![Contenedor CCW y contenedor RCW](./media/interop-marshaling/interop-direct-ref-across-process.gif "Paso de referencia entre límites de hosts y procesos")

En esta ilustración:

- Un cliente no administrado obtiene una referencia a un objeto COM de un objeto administrado que obtiene esta referencia de un host remoto. El mecanismo de comunicación remota es DCOM.
- Un cliente administrado obtiene una referencia a un objeto administrado de un objeto COM que obtiene esta referencia de un host remoto. El mecanismo de comunicación remota es DCOM.

    > [!NOTE]
    > La biblioteca de tipos exportada del servidor administrado debe estar registrada.

El número de límites de procesos entre llamador y destinatario es irrelevante; la misma referencia directa se produce para las llamadas en proceso y fuera de proceso.

### <a name="managed-remoting"></a>Comunicación remota administrada

El runtime también proporciona comunicación remota administrada que puede usarse para establecer un canal de comunicaciones entre objetos administrados a través varios procesos y límites de hosts. La comunicación remota administrada puede hospedar un firewall entre los componentes de la comunicación, como se muestra en la siguiente ilustración:

![SOAP o TcpChannel](./media/interop-marshaling/interop-remote-soap-or-tcp.gif "Llamadas remotas a través de firewalls que usan SOAP o la clase TcpChannel") Llamadas remotas a través de firewalls que usan SOAP o la clase TcpChannel

Algunas llamadas no administradas pueden canalizarse mediante SOAP, como las llamadas entre componentes de servicio y COM.

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Comportamiento predeterminado del cálculo de referencias](default-marshaling-behavior.md)|Describe las reglas que usa el servicio de serialización de interoperabilidad para serializar datos.|
|[Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md)|Describe cómo se declaran parámetros de método y se pasan argumentos a funciones exportadas por bibliotecas no administradas.|
|[Serialización de datos con la interoperabilidad COM](marshaling-data-with-com-interop.md)|Describe cómo se personalizan los contenedores COM para alterar el comportamiento de la serialización.|
|[Cómo: Migrar código administrado DCOM a WCF](how-to-migrate-managed-code-dcom-to-wcf.md)|Describe cómo se migra de DCOM a WCF.|
|[Cómo: Asignar resultados HRESULT y excepciones](how-to-map-hresults-and-exceptions.md)|Describe cómo se asignan excepciones personalizadas a valores HRESULT y proporciona la asignación completa de cada HRESULT a su clase de excepción comparable en .NET Framework.|
|[Interoperar mediante tipos genéricos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))|Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.|
|[Interoperar con código no administrado](index.md)|Describe los servicios de interoperabilidad proporcionados por Common Language Runtime.|
|[Interoperabilidad COM avanzada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))|Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.|
|[Consideraciones de diseño para interoperaciones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))|Proporciona sugerencias para escribir componentes COM integrados.|

## <a name="reference"></a>Referencia

<xref:System.Runtime.InteropServices?displayProperty=nameWithType>
