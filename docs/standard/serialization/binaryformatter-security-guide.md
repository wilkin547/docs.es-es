---
title: Guía de seguridad de BinaryFormatter
description: En este artículo se describen los riesgos de seguridad inherentes al tipo BinaryFormatter y las recomendaciones para que lo usen los diferentes serializadores.
ms.date: 07/11/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: 2c76a81650e5b83677f6c4df64770bd1ef5f775e
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88607935"
---
# <a name="binaryformatter-security-guide"></a>Guía de seguridad de BinaryFormatter

Este artículo se aplica a la implementaciones de .NET siguientes:

* .NET Framework (todas las versiones)
* .NET Core 2.1 a 3.1
* .NET 5.0 y versiones posteriores

## <a name="background"></a>Fondo

> [!WARNING]
> El tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> es peligroso y ***no*** se recomienda para el procesamiento de datos. Las aplicaciones deben dejar de usar `BinaryFormatter` lo antes posible, aunque crean que los datos que procesan son de confianza. `BinaryFormatter` no es seguro y no se puede convertir en seguro.

Este artículo también se aplica a los tipos siguientes:

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Web.UI.ObjectStateFormatter>

Las vulnerabilidades de deserialización son una categoría de amenazas donde las cargas de solicitud se procesan sin seguridad. Un atacante que aprovecha correctamente estas vulnerabilidades en una aplicación puede provocar ataques por denegación de servicio (DoS), la divulgación de información o la ejecución remota de código dentro de la aplicación de destino. Esta categoría de riesgo se engloba dentro de [OWASP Top 10](https://owasp.org/www-project-top-ten/). Los destinos incluyen aplicaciones escritas en [diversos lenguajes](https://owasp.org/www-community/vulnerabilities/Deserialization_of_untrusted_data), incluidos C/C++, Java y C#.

En .NET, el mayor destino de riesgo son las aplicaciones que usan el tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para deserializar datos. `BinaryFormatter` se utiliza ampliamente en todo el ecosistema de .NET debido a su eficacia y facilidad de uso. Pero esta misma eficacia ofrece a los atacantes la posibilidad de influir en el flujo de control dentro de la aplicación de destino. Los ataques correctos pueden dar lugar a que el atacante pueda ejecutar código en el contexto del proceso de destino.

Como analogía más simple, imagine que la llamada a `BinaryFormatter.Deserialize` sobre una carga es equivalente a interpretar esa carga como un archivo ejecutable independiente e iniciarlo.

## <a name="binaryformatter-security-vulnerabilities"></a>Vulnerabilidades de seguridad de BinaryFormatter

> [!WARNING]
> El método `BinaryFormatter.Deserialize` __nunca__ es seguro cuando se usa con una entrada que no es de confianza. Se recomienda encarecidamente que los consumidores consideren el uso de una de las alternativas que se describen más adelante en este artículo.

`BinaryFormatter` se implementó antes de que las vulnerabilidades de deserialización fueran una categoría de amenaza bien entendida. Como resultado, el código no sigue los procedimientos recomendados modernos. El método `Deserialize` se puede usar como un vector para que los atacantes realicen ataques DoS contra aplicaciones de consumo. Es posible que estos ataques hagan que la aplicación deje de responder o que se produzca una terminación inesperada del proceso. Esta categoría de ataque no se puede mitigar con `SerializationBinder` o con cualquier otro modificador de configuración `BinaryFormatter`. .NET considera que este comportamiento es ***por definición*** y no emitirá una actualización de código para modificarlo.

`BinaryFormatter.Deserialize` puede ser vulnerable a otras categorías de ataque, como la divulgación de información o la ejecución remota de código. El uso de características como un elemento <xref:System.Runtime.Serialization.SerializationBinder> personalizado puede ser insuficiente para mitigar estos riesgos de forma correcta. Existe la posibilidad de que se detecte una vulnerabilidad nueva para la que .NET no pueda publicar de forma práctica una actualización de seguridad. Los consumidores deben evaluar sus escenarios individuales y considerar su posible exposición a estos riesgos.

Se recomienda que los consumidores de `BinaryFormatter` realicen valoraciones de riesgo individuales en sus aplicaciones. Es responsabilidad exclusiva del consumidor determinar si se usa `BinaryFormatter`. Los consumidores deben evaluar el riesgo de los requisitos de seguridad, técnicos, de reputación, legales y normativos del uso de `BinaryFormatter`.

## <a name="preferred-alternatives"></a>Alternativas preferidas

.NET ofrece varios serializadores integrados que pueden administrar de forma segura los datos que no son de confianza:

* <xref:System.Xml.Serialization.XmlSerializer> y <xref:System.Runtime.Serialization.DataContractSerializer> para serializar gráficos de objetos en y desde XML. No se debe confundir `DataContractSerializer` con <xref:System.Runtime.Serialization.NetDataContractSerializer>.
* <xref:System.IO.BinaryReader> y <xref:System.IO.BinaryWriter> para XML y JSON.
* Las API de <xref:System.Text.Json> para serializar gráficos de objetos en JSON.

## <a name="dangerous-alternatives"></a>Alternativas peligrosas

Evite los siguientes serializadores:

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.ObjectStateFormatter>

Los serializadores anteriores realizan una deserialización polimórfica sin restricciones y son peligrosos, como `BinaryFormatter`.

## <a name="the-risks-of-assuming-data-to-be-trustworthy"></a>Riesgos de asumir que los datos son de confianza

Con frecuencia, un desarrollador de aplicaciones podría creer que solo procesa entradas de confianza. El caso de la entrada segura es cierto en algunas circunstancias poco frecuentes. Pero es mucho más común que una carga cruce un límite de confianza sin que el desarrollador sea consciente de ello.

__Le recomendamos que use un servidor local__ en el que los empleados usan un cliente de escritorio desde sus estaciones de trabajo para interactuar con el servicio. Este escenario se podría considerar ingenuamente como una configuración "segura" en la que es aceptable usar `BinaryFormatter`. Pero este escenario presenta un vector de malware que obtiene acceso al equipo de un único empleado para poder propagarse por toda la empresa. Ese malware puede aprovechar el uso de `BinaryFormatter` de la empresa para después moverse lateralmente desde la estación de trabajo del empleado hasta el servidor de back-end. Luego, puede extraer datos confidenciales de la empresa, como secretos comerciales o datos de clientes.

__Considere también una aplicación que use `BinaryFormatter` para conservar el estado de guardado.__ Esto podría parecer inicialmente un escenario seguro, ya que la lectura y escritura de datos en una unidad de disco duro propia representa una amenaza menor. Pero es habitual compartir documentos por correo electrónico o Internet, y la mayoría de los usuarios finales no perciben que abrir estos archivos descargados sea un comportamiento arriesgado.

Este escenario se puede aprovechar con un efecto malintencionado. Si la aplicación es un juego, los usuarios que comparten archivos de guardado se ponen en riesgo sin saberlo. Los propios desarrolladores también pueden ser el objetivo. El atacante podría enviar un correo electrónico al soporte técnico de los desarrolladores, adjuntar un archivo de datos malintencionado y pedir al personal de soporte técnico que lo abra. Este tipo de ataque podría servir al atacante para adentrarse en la empresa.

Otro escenario es cuando el archivo de datos se encuentra en el almacenamiento en la nube y se sincroniza de forma automática entre los equipos del usuario. Un atacante que consiga obtener acceso a la cuenta de almacenamiento en la nube puede envenenar el archivo de datos. Este archivo de datos se sincronizará automáticamente con los equipos del usuario. La próxima vez que el usuario abra el archivo de datos, se ejecutará la carga del atacante. Por tanto, el atacante puede aprovechar un riesgo de la cuenta de almacenamiento en la nube para obtener permisos de ejecución de código completos.

__Considere una aplicación que pase de un modelo de instalación de escritorio a un modelo de primero en la nube.__ Este escenario incluye aplicaciones que se mueven desde una aplicación de escritorio o un modelo de cliente enriquecido a un modelo basado en web. Los modelos de amenazas descritos para la aplicación de escritorio no se aplican necesariamente al servicio basado en la nube. Es posible que en el modelo de amenazas de la aplicación de escritorio se descarte una amenaza concreta como "no interesante para que el cliente se ataque a sí mismo". Pero esa misma amenaza podría resultar interesante cuando considera que un usuario remoto (el cliente) ataca al propio servicio en la nube.

> [!NOTE]
> En términos generales, la intención de la serialización es transmitir un objeto dentro o fuera de una aplicación. Un ejercicio de modelado de amenazas casi siempre marca este tipo de transferencia de datos como el cruce de un límite de confianza.

## <a name="further-resources"></a>Recursos adicionales

* [YSoSerial.Net](https://github.com/pwntester/ysoserial.net) para investigar cómo los adversarios atacan las aplicaciones que usan `BinaryFormatter`.
* Información general sobre vulnerabilidades de deserialización:
  * [OWASP Top 10: A8:2017 - Deserialización no segura](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A8-Insecure_Deserialization)
  * [CWE-502: Deserialización de datos que no son de confianza](https://cwe.mitre.org/data/definitions/502.html)
