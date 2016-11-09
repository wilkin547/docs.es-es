---
title: "Protocolo de comunicación de prueba de la CLI de .NET Core"
description: "Protocolo de comunicación de prueba de la CLI de .NET Core"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 88cba792-3640-41de-b55d-00f575e9d5e2
translationtype: Human Translation
ms.sourcegitcommit: 81e7604f0a646e5de9c2ed35ff3b6ef6d7fb2e71
ms.openlocfilehash: a35385cbb08614493fdcfc74504b00178dc532ea

---

#<a name="net-core-cli-test-communication-protocol"></a>Protocolo de comunicación de prueba de la CLI de .NET Core

## <a name="introduction"></a>Introducción
Cada vez que pasa un puerto a prueba de dotnet, el comando se ejecutará en tiempo de diseño. Eso significa que la prueba de dotnet se conectará a ese puerto a través de TCP y, luego, intercambiará un conjunto establecido de mensajes con lo que sea que esté conectado a ese puerto. Cuando esto sucede, el ejecutor también recibe un puerto nuevo que la prueba de dotnet usará para comunicarse con él. El ejecutor también usa TCP para comunicarse con la prueba de dotnet porque, en el modo de diseño, no resulta suficiente solo mostrar los resultados en la consola. El comando necesita enviar los mensajes de la estructura del adaptador que contienen los resultados de la ejecución de la prueba.

### <a name="communication-protocol-at-design-time"></a>Protocolo de comunicación en tiempo de diseño.

1. Como durante el tiempo de diseño, la prueba de dotnet se conecta a un puerto cuando se inicia, el adaptador debe escuchar en ese puerto; de lo contrario, la prueba de dotnet generará un error. Esto se diseñó así para que el adaptador pudiera reservar todos los puertos necesarios al enlazarse con ellos y escucharlos antes de que la prueba de dotnet se ejecute e intente obtener los puertos para el ejecutor.
2. Una vez que se inicia la prueba de dotnet, envía un mensaje de tipo TestSession.Connected al adaptador para indicar que está preparada para recibir mensajes.
3. Es posible enviar un mensaje de [comprobación de la versión](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/ProtocolVersionMessage.cs) con la versión del adaptador del protocolo en él. La prueba de dotnet enviará de vuelta la versión del protocolo que admite.

Todos los mensajes tienen este formato: [Message.cs](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/Message.cs). Los formatos de carga de cada mensaje se describen en los vínculos a las clases que se usan para serializar/deserializar la información que aparece en la descripción del protocolo.

#### <a name="test-execution"></a>Ejecución de pruebas
![Ejecución de pruebas](./media/test-protocol/dotnet-test-execute.png)

1. Después de la comprobación opcional de la versión, el adaptador envía un mensaje de tipo TestExecution.GetTestRunnerProcessStartInfo, con la [prueba](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs) que desea ejecutar dentro. La prueba de dotnet envía de vuelta un nombre de archivo y argumentos dentro de una carga de tipo [TestStartInfo](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.DotNet.Tools.Test/TestStartInfo.cs) que el adaptador puede usar para iniciar el ejecutor. Anteriormente, habríamos enviado la lista de las pruebas a ejecutar como parte de ese argumento pero, en realidad, habríamos superado el límite de tamaño de la línea de comandos en algunos proyectos de prueba.
  1. Como parte de los argumentos, enviamos un puerto al que se debe conectar el ejecutor y, para la ejecución de las pruebas, una marca de tipo --wait-command, que indica que el ejecutor se debe conectar al puerto y esperar los comandos, en lugar de avanzar y ejecutar las pruebas.
2. En este punto, el adaptador puede iniciar el ejecutor (y conectarse a él para realizar una depuración, si decide hacerlo).
3. Una vez que se inicia el ejecutor, envía a la prueba de dotnet un mensaje de tipo TestRunner.WaitCommand que indica que está preparado para recibir comandos, en cuyo caso la prueba de dotnet envía un mensaje de tipo TestRunner.Execute con la lista de las [pruebas](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs) que se deben ejecutar. Con esto se omite el límite de tamaño de la línea de comandos que se describió anteriormente.
4. Luego, el ejecutor envía a la prueba de dotnet (y pasa al adaptador) un mensaje de tipo TestExecution.TestStarted para cada prueba a medida que se inicia con la información sobre la [prueba](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Test.cs) dentro de él.
5. El ejecutor también envía a la prueba de dotnet (y pasa al adaptador) un mensaje de tipo TestExecution.TestResult para cada prueba con el [resultado individual](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/TestResult.cs) de la misma.
6. Una vez que se realizan todas las pruebas, el ejecutor envía un mensaje de tipo TestRunner.Completed a la prueba de dotnet que, a su vez, lo envía como mensaje de tipo TestExecution.Completed al adaptador.
7. Una vez que el adaptador está listo, envía a la prueba de dotnet un mensaje de tipo TestSession.Terminate, el que hará que la prueba de dotnet se apague.

#### <a name="test-discovery"></a>Detección de pruebas
![Detección de pruebas](./media/test-protocol/dotnet-test-discover.png)

1. Después de la comprobación opcional de la versión, el adaptador envía un mensaje de tipo TestDiscovery.Start. Como en este caso el adaptador no necesita conectarse al proceso, la prueba de dotnet iniciará el ejecutor mismo. Además, y debido a que no se debe pasar ninguna lista larga de argumentos al ejecutor, no es necesario pasar ninguna marca --wait-command al ejecutor. La prueba de dotnet solo pasa un argumento --list al ejecutor, lo que significa que el ejecutor no debe ejecutar las pruebas, sino que solo mostrarlas.
2. Luego, el ejecutor envía a la prueba de dotnet (y pasa al adaptador) un mensaje de tipo TestDiscovery.TestFound para cada [prueba](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Test.cs) que se encuentra.
3. Una vez que se realizan todas las pruebas, el ejecutor envía un mensaje de tipo TestRunner.Completed a la prueba de dotnet que, a su vez, lo envía como mensaje de tipo TestDiscovery.Completed al adaptador.
4. Una vez que el adaptador está listo, envía a la prueba de dotnet un mensaje de tipo TestSession.Terminate, el que hará que la prueba de dotnet se apague.


<!--HONumber=Nov16_HO1-->


