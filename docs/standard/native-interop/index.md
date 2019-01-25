---
title: 'Interoperabilidad nativa: .NET'
description: Obtenga información sobre cómo interactuar con componentes nativos en .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 29aacc9210b4103f379b7776c36fc3c29b9e6dec
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857624"
---
# <a name="native-interoperability"></a><span data-ttu-id="653c6-103">Interoperabilidad nativa</span><span class="sxs-lookup"><span data-stu-id="653c6-103">Native interoperability</span></span>

<span data-ttu-id="653c6-104">En los artículos siguientes se muestran varios métodos para hacer "interoperabilidad nativa" en .NET.</span><span class="sxs-lookup"><span data-stu-id="653c6-104">The following articles show the various ways of doing "native interoperability" in .NET.</span></span>

<span data-ttu-id="653c6-105">Existen varios motivos por los que puede interesarle llamar a código nativo:</span><span class="sxs-lookup"><span data-stu-id="653c6-105">There are a few reasons why you'd want to call into native code:</span></span>

* <span data-ttu-id="653c6-106">Los sistemas operativos incluyen un elevado volumen de API que no están presentes en las bibliotecas de clases administradas.</span><span class="sxs-lookup"><span data-stu-id="653c6-106">Operating systems come with a large volume of APIs that aren't present in the managed class libraries.</span></span> <span data-ttu-id="653c6-107">Un buen ejemplo de este escenario sería el acceso al hardware o a funciones de administración del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="653c6-107">A prime example for this scenario would be access to hardware or operating system management functions.</span></span>
* <span data-ttu-id="653c6-108">La comunicación con otros componentes que tienen o que pueden producir ABI de estilo C (ABI nativos), como el código Java expuesto mediante [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) o cualquier otro lenguaje administrado que podría producir un componente nativo.</span><span class="sxs-lookup"><span data-stu-id="653c6-108">Communicating with other components that have or can produce C-style ABIs (native ABIs), such as Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
* <span data-ttu-id="653c6-109">En Windows, la mayor parte del software que se instala, como el conjunto de aplicaciones de Microsoft Office, registra los componentes COM que representan sus programas y permiten a los desarrolladores automatizarlos o usarlos.</span><span class="sxs-lookup"><span data-stu-id="653c6-109">On Windows, most of the software that gets installed, such as the Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="653c6-110">Esto también requiere interoperabilidad nativa.</span><span class="sxs-lookup"><span data-stu-id="653c6-110">This also requires native interoperability.</span></span>

<span data-ttu-id="653c6-111">La lista anterior no cubre todas las posibles situaciones y escenarios en los que el desarrollador puede querer o necesitar interactuar con componentes nativos.</span><span class="sxs-lookup"><span data-stu-id="653c6-111">The previous list doesn't cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="653c6-112">La biblioteca de clases. NET, por ejemplo, usa la compatibilidad con la interoperabilidad nativa para implementar bastantes de sus API, como la compatibilidad con la consola y su manipulación, el acceso al sistema de archivos, etc.</span><span class="sxs-lookup"><span data-stu-id="653c6-112">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="653c6-113">Pero es importante que tenga en cuenta que tiene la opción, en caso de que la necesite.</span><span class="sxs-lookup"><span data-stu-id="653c6-113">However, it's important to note that there's an option if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="653c6-114">La mayoría de los ejemplos de esta sección se presentarán para las tres plataformas compatibles con .NET Core (Windows, Linux y macOS).</span><span class="sxs-lookup"><span data-stu-id="653c6-114">Most of the examples in this section will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="653c6-115">En cambio, en algunos ejemplos breves e ilustrativos solo se muestra un ejemplo que usa nombres de archivo y extensiones de Windows (es decir, "dll" en el caso de las bibliotecas).</span><span class="sxs-lookup"><span data-stu-id="653c6-115">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="653c6-116">Esto no significa que esas características no estén disponibles en Linux o macOS, sino que simplemente se buscaba una mayor comodidad.</span><span class="sxs-lookup"><span data-stu-id="653c6-116">This doesn't mean that those features aren't available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="see-also"></a><span data-ttu-id="653c6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="653c6-117">See also</span></span>

- [<span data-ttu-id="653c6-118">Invocación de plataforma (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="653c6-118">Platform Invoke (P/Invoke)</span></span>](pinvoke.md)
- [<span data-ttu-id="653c6-119">Serialización de tipos</span><span class="sxs-lookup"><span data-stu-id="653c6-119">Type marshalling</span></span>](type-marshalling.md)
- [<span data-ttu-id="653c6-120">Procedimientos recomendados de interoperabilidad nativa</span><span class="sxs-lookup"><span data-stu-id="653c6-120">Native interoperability best practices</span></span>](best-practices.md)
