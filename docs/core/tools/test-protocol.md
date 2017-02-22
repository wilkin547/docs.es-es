---
title: "Protocolo de comunicación de prueba de la CLI de .NET Core | Microsoft Docs"
description: "Protocolo de comunicación de prueba de la CLI de .NET Core"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88cba792-3640-41de-b55d-00f575e9d5e2
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 83555650a5a3ce9ed28d329aa82f5ead75e2d9cb

---

#<a name="net-core-cli-test-communication-protocol"></a>Protocolo de comunicación de prueba de la CLI de .NET Core

> [!WARNING]
> Este tema se aplica a .NET Core Tools Preview 2. Para la documentación de .NET Core Tools RC4, consulte el tema [Herramientas de la interfaz de la línea de comandos de .NET Core (.NET Core Tools RC4)](../preview3/tools/index.md).

## <a name="introduction"></a>Introducción
Cada vez que pasa un puerto a prueba de dotnet, el comando se ejecutará en tiempo de diseño. Eso significa que `dotnet test` se conectará a ese puerto a través de TCP y, luego, intercambiará un conjunto establecido de mensajes con lo que sea que esté conectado a ese puerto. Cuando esto sucede, el ejecutor también recibe un puerto nuevo que `dotnet test` usará para comunicarse con él. El ejecutor también usa TCP para comunicarse con `dotnet test` porque, en el modo de diseño, no basta con mostrar los resultados en la consola. El comando necesita enviar los mensajes de la estructura del adaptador que contienen los resultados de la ejecución de la prueba.

### <a name="communication-protocol-at-design-time"></a>Protocolo de comunicación en tiempo de diseño.

1. Como durante el tiempo de diseño, `dotnet test` se conecta a un puerto cuando se inicia, el adaptador debe escuchar en ese puerto; de lo contrario, `dotnet test` generará un error. Esto se diseñó así para que el adaptador pudiera reservar todos los puertos necesarios al enlazarse con ellos y escucharlos antes de que `dotnet test` se ejecute e intente obtener los puertos para el ejecutor.
2. Una vez que se inicia `dotnet test`, envía un mensaje de tipo TestSession.Connected al adaptador para indicar que está preparada para recibir mensajes.
3. Es posible enviar un mensaje de [comprobación de la versión](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/ProtocolVersionMessage.cs) con la versión del adaptador del protocolo en él. `dotnet test` enviará de vuelta la versión del protocolo que admite.

Todos los mensajes tienen este formato: [Message.cs](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/Message.cs). Los formatos de carga de cada mensaje se describen en los vínculos a las clases que se usan para serializar/deserializar la información que aparece en la descripción del protocolo.

#### <a name="test-execution"></a>Ejecución de pruebas
![Ejecución de pruebas](./media/test-protocol/dotnet-test-execute.png)

1. Después de la comprobación opcional de la versión, el adaptador envía un mensaje de tipo TestExecution.GetTestRunnerProcessStartInfo, con la [prueba](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs) que desea ejecutar dentro. `dotnet test` envía de vuelta un nombre de archivo y argumentos dentro de una carga de tipo [TestStartInfo](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/dotnet/commands/dotnet-test/TestStartInfo.cs) que el adaptador puede usar para iniciar el ejecutor. Anteriormente, habríamos enviado la lista de las pruebas a ejecutar como parte de ese argumento pero, en realidad, habríamos superado el límite de tamaño de la línea de comandos en algunos proyectos de prueba.
  1. Como parte de los argumentos, enviamos un puerto al que se debe conectar el ejecutor y, para la ejecución de las pruebas, una marca de tipo --wait-command, que indica que el ejecutor se debe conectar al puerto y esperar los comandos, en lugar de avanzar y ejecutar las pruebas.
2. En este punto, el adaptador puede iniciar el ejecutor (y conectarse a él para realizar una depuración, si decide hacerlo).
3. Una vez que se inicia el ejecutor, envía a `dotnet test` un mensaje de tipo TestRunner.WaitCommand que indica que está preparado para recibir comandos, en cuyo caso `dotnet test` envía un mensaje de tipo TestRunner.Execute con la lista de [pruebas](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs) que se deben ejecutar. Con esto se omite el límite de tamaño de la línea de comandos que se describió anteriormente.
4. Luego, el ejecutor envía a `dotnet test` (y pasa al adaptador) un mensaje de tipo TestExecution.TestStarted para cada prueba a medida que se inicia, con la información sobre la [prueba](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Test.cs) dentro de él.
5. El ejecutor también envía a `dotnet test` (y pasa al adaptador) un mensaje de tipo TestExecution.TestResult para cada prueba con el [resultado individual](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/TestResult.cs) de la misma.
6. Una vez que se realizan todas las pruebas, el ejecutor envía un mensaje de tipo TestRunner.Completed a `dotnet test` que, a su vez, lo envía como mensaje de tipo TestExecution.Completed al adaptador.
7. Cuando el adaptador está listo, envía a `dotnet test` un mensaje de tipo TestSession.Terminate para que `dotnet test` se apague.

#### <a name="test-discovery"></a>Detección de pruebas
![Detección de pruebas](./media/test-protocol/dotnet-test-discover.png)

1. Después de la comprobación opcional de la versión, el adaptador envía un mensaje de tipo TestDiscovery.Start. Como en este caso el adaptador no necesita conectarse al proceso, `dotnet test` iniciará el ejecutor mismo. Además, y debido a que no se debe pasar ninguna lista larga de argumentos al ejecutor, no es necesario pasar ninguna marca --wait-command al ejecutor. `dotnet test` solo pasa un argumento --list al ejecutor, lo que significa que el ejecutor no debe ejecutar las pruebas, tan solo mostrarlas.
2. Luego, el ejecutor envía a `dotnet test` (y pasa al adaptador) un mensaje de tipo TestDiscovery.TestFound para cada [prueba](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Test.cs) que se encuentra.
3. Una vez que se realizan todas las pruebas, el ejecutor envía un mensaje de tipo TestRunner.Completed a `dotnet test` que, a su vez, envía un mensaje de tipo TestDiscovery.Completed al adaptador.
4. Cuando el adaptador está listo, envía a `dotnet test` un mensaje de tipo TestSession.Terminate para que `dotnet test` se apague.



<!--HONumber=Feb17_HO2-->


