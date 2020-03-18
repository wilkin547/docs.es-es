---
title: 'Interoperabilidad nativa: .NET'
description: Obtenga información sobre cómo interactuar con componentes nativos en .NET.
ms.date: 01/18/2019
ms.openlocfilehash: 330466d74cc268214f74c4f575e6a2961f678972
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706340"
---
# <a name="native-interoperability"></a>Interoperabilidad nativa

En los artículos siguientes se muestran varios métodos para hacer "interoperabilidad nativa" en .NET.

Existen varios motivos por los que puede interesarle llamar a código nativo:

- Los sistemas operativos incluyen un elevado volumen de API que no están presentes en las bibliotecas de clases administradas. Un buen ejemplo de este escenario sería el acceso al hardware o a funciones de administración del sistema operativo.
- La comunicación con otros componentes que tienen o que pueden producir ABI de estilo C (ABI nativos), como el código Java expuesto mediante [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) o cualquier otro lenguaje administrado que podría producir un componente nativo.
- En Windows, la mayor parte del software que se instala, como el conjunto de aplicaciones de Microsoft Office, registra los componentes COM que representan sus programas y permiten a los desarrolladores automatizarlos o usarlos. Esto también requiere interoperabilidad nativa.

La lista anterior no cubre todas las posibles situaciones y escenarios en los que el desarrollador puede querer o necesitar interactuar con componentes nativos. La biblioteca de clases. NET, por ejemplo, usa la compatibilidad con la interoperabilidad nativa para implementar bastantes de sus API, como la compatibilidad con la consola y su manipulación, el acceso al sistema de archivos, etc. Pero es importante que tenga en cuenta que tiene la opción, en caso de que la necesite.

> [!NOTE]
> La mayoría de los ejemplos de esta sección se presentarán para las tres plataformas compatibles con .NET Core (Windows, Linux y macOS). En cambio, en algunos ejemplos breves e ilustrativos solo se muestra un ejemplo que usa nombres de archivo y extensiones de Windows (es decir, "dll" en el caso de las bibliotecas). Esto no significa que esas características no estén disponibles en Linux o macOS, sino que simplemente se buscaba una mayor comodidad.

## <a name="see-also"></a>Vea también

- [Invocación de plataforma (P/Invoke)](pinvoke.md)
- [Serialización de tipos](type-marshaling.md)
- [Procedimientos recomendados de interoperabilidad nativa](best-practices.md)
