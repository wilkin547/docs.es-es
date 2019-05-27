---
title: Recopilación de telemetría mediante la CLI de ML.NET
description: Descubra las características de telemetría de la CLI de ML.NET que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlas. Además, encuentre vínculos al contrato de licencia de .NET, así como información sobre el cumplimiento de Microsoft del RGPD.
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 49ebd6c9e1b77c85d891b8c9fb8cbd5c66b478a9
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065548"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a>Recopilación de telemetría mediante la CLI de ML.NET

La [CLI de ML.NET](http://aka.ms/mlnet-cli) incluye una característica de telemetría que recopila datos de uso anónimos que se agregan para su uso por parte de Microsoft.

## <a name="how-microsoft-uses-the-data"></a>Cómo Microsoft usa los datos

El equipo del producto usa los datos de telemetría de la CLI de ML.NET para ayudar a entender cómo mejorar las herramientas. Por ejemplo, si los clientes usan con poca frecuencia determinada tarea de aprendizaje de automático, el equipo del producto investiga por qué y usa las conclusiones para dar prioridad al desarrollo de características. La telemetría de la CLI de ML.NET también ayuda con la depuración de problemas, como bloqueos y anomalías de código. 

Mientras que el equipo del producto valora esta información, también sabemos que no todos desean enviar estos datos. [Averigüe cómo deshabilitar la telemetría.](#opt-out-of-data-collection)

## <a name="scope"></a>Ámbito

El comando `mlnet` inicia la CLI de ML.NET, pero el comando por sí mismo no recopila la telemetría.

La telemetría *no está habilitada* cuando se ejecuta el comando `mlnet` sin ningún comando asociado. Por ejemplo:

- `mlnet`
- `mlnet --help`

La telemetría *está habilitada* al ejecutar un [comando de la CLI de ML.NET](../reference/ml-net-cli-reference.md), tal como `mlnet auto-train`.

## <a name="opt-out-of-data-collection"></a>No participar en la recopilación de datos

La característica de telemetría de la CLI de ML.NET está habilitada de manera predeterminada.

Puede desactivar la característica de telemetría si establece la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`. Esta variable de entorno se aplica globalmente a la herramienta de la CLI de .NET.

## <a name="data-points-collected"></a>Punto de datos recopilados

La característica recopila los siguientes datos:

- Los comandos que se invocan, como `auto-train`
- Dirección MAC con hash: un id. único y anónimo criptográficamente (SHA256) para una máquina
- Marca de tiempo de una invocación
- Dirección IP de tres octetos usada solo para determinar la ubicación geográfica
- Nombre de todos los argumentos y parámetros utilizados. No los valores del cliente, como las cadenas
- Sistema operativo y versión
- Valor del parámetro --ml-task: Valores categóricos, como `regression`, `binary-classification`, y `multiclass-classification`
- Tamaño de archivo del conjunto de datos de [logarítmica redondeada](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) (a la potencia al cuadrado más próxima)
- `ExitCode` del comando

Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Azure Application Insights](https://azure.microsoft.com/services/application-insights/), se conservan bajo acceso restringido y se utilizan bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).

### <a name="data-points-not-collected"></a>Punto de datos no recopilados
La característica de telemetría *no* recopila:
- datos personales, como los nombres de usuario
- nombres de archivo de conjunto de datos
- datos de los archivos del conjunto de datos

Si sospecha que la telemetría de la CLI de ML.NET recopila datos confidenciales o que los datos se están tratando de forma insegura o inapropiada, informe de un problema en los problemas del repositorio de [ML.NET](https://github.com/dotnet/machinelearning) para que lo investiguemos.

## <a name="license"></a>Licencia

La distribución de Microsoft de la CLI de ML.NET cuenta con licencia en virtud de los [términos de licencia del software de Microsoft: biblioteca de Microsoft .NET](https://aka.ms/dotnet-core-eula). Para obtener más información sobre la recolección y el procesamiento de datos, vea la sección titulada "Datos".

## <a name="disclosure"></a>Divulgación

Al ejecutar por primera vez un [comando de la CLI de ML.NET](../reference/ml-net-cli-reference.md) como `mlnet auto-train`, la herramienta de la CLI de ML.NET muestra el texto de divulgación que indica cómo dejar de participar en la telemetría. El texto puede variar ligeramente según la versión de la CLI que ejecute.

## <a name="see-also"></a>Vea también
- [Referencia de la CLI de ML.NET](../reference/ml-net-cli-reference.md)
- [Términos de licencia del software de Microsoft: biblioteca de Microsoft .NET](https://aka.ms/dotnet-core-eula)
- [Privacidad en Microsoft](https://www.microsoft.com/en-us/trustcenter/privacy/)
- [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/en-us/privacystatement)
