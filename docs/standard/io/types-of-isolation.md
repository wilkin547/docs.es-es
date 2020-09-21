---
title: Tipos de aislamiento
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- storing data using isolated storage, accessing isolated storage
- storing data using isolated storage, isolation types
- authentication [.NET Framework], isolated storage
- assemblies [.NET Framework], identity
- isolated storage, accessing
- data storage using isolated storage, isolation types
- data storage using isolated storage, accessing isolated storage
- domain identity
- isolated storage, types
- user authentication, isolated storage
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
ms.openlocfilehash: 244bd9c25040b39c9349d28f57981f29d7a32d0a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542039"
---
# <a name="types-of-isolation"></a>Tipos de aislamiento
El acceso al almacenamiento aislado siempre está restringido al usuario que lo creó. Para implementar este tipo de aislamiento, Common Language Runtime usa el mismo concepto de identidad de usuario que reconoce el sistema operativo, que es la identidad asociada con el proceso en el que se ejecuta el código cuando se abre el almacén. Esta identidad es una identidad de usuario autenticado, pero la suplantación puede hacer que la identidad del usuario actual cambie de forma dinámica.  
  
 El acceso al almacenamiento aislado también está restringido por la identidad asociada con el dominio y el ensamblado de la aplicación, o solo con el ensamblado. El tiempo de ejecución obtiene estas identidades de las maneras siguientes:  
  
- La identidad de dominio representa la evidencia de la aplicación, que en el caso de una aplicación web podría ser la dirección URL completa. Para el código hospedado en el shell, la identidad de dominio podría basarse en la ruta de acceso del directorio de la aplicación. Por ejemplo, si se ejecuta el ejecutable desde la ruta de acceso C:\Office\MyApp.exe, la identidad de dominio sería C:\Office\MyApp.exe.  
  
- Identidad del ensamblado es la evidencia del ensamblado. Esto podría proceder de una firma digital criptográfica, que puede ser el [nombre seguro](../assembly/strong-named.md) del ensamblado, el editor de software del ensamblado o su identidad de dirección URL. Si un ensamblado tiene un nombre seguro y una identidad del editor de software, se utiliza la identidad del editor de software. Si el ensamblado procede de Internet y no está firmado, se utiliza la identidad de dirección URL. Para obtener más información sobre los ensamblados y nombres seguros, vea [Programar con ensamblados](../assembly/index.md).  
  
- Los almacenes móviles se mueven con un usuario que tenga un perfil de usuario móvil. Los archivos se escriben en un directorio de red y se descargan en cualquier equipo en que el usuario inicia sesión. Para obtener más información sobre los perfiles de usuarios móviles, consulte <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.  
  
 Mediante la combinación de los conceptos de usuario, dominio e identidad de ensamblado, el almacenamiento aislado puede aislar los datos de las siguientes formas, cada una de las cuales tiene sus propios escenarios de uso:  
  
- [Aislamiento por usuario y ensamblado](#UserAssembly)  
  
- [Aislamiento por usuario, dominio y ensamblado](#UserDomainAssembly)  
  
 Cualquiera de estos aislamientos se puede combinar con un perfil de usuario móvil. Para obtener más información, vea la sección [Aislamiento aislado y movilidad](#Roaming).  
  
 En la siguiente ilustración se muestra cómo se aíslan los almacenes en distintos ámbitos:  
  
 ![Diagrama que muestra el aislamiento por usuario y ensamblado.](./media/types-of-isolation/isolated-storage-types.gif)  
  
 Con la excepción de los almacenes móviles, el equipo siempre aísla de forma implícita el almacenamiento aislado, porque usa los medios de almacenamiento locales en un equipo determinado.  
  
> [!IMPORTANT]
> El almacenamiento aislado no está disponible para las aplicaciones de la Tienda Windows 8.x. En su lugar, use las clases de datos de la aplicación de los espacios de nombres `Windows.Storage` incluidas en la API de Windows Runtime para almacenar archivos y datos locales. Para más información, vea [Datos de aplicación](/previous-versions/windows/apps/hh464917(v=win.10)) en el Centro de desarrollo de Windows.  
  
<a name="UserAssembly"></a>
## <a name="isolation-by-user-and-assembly"></a>Aislamiento por usuario y ensamblado  
 Cuando es necesario acceder al ensamblado que usa el almacén de datos desde cualquier dominio de la aplicación, el aislamiento por usuario y ensamblado es adecuado. Normalmente, en esta situación, el almacenamiento aislado se usa para almacenar datos que se aplican en varias plataformas y no está vinculado a ninguna aplicación concreta, como el nombre del usuario o la información de licencia. Para acceder al almacenamiento aislado por usuario y ensamblado, el código debe ser de confianza para transferir información entre aplicaciones. Por lo general, se permite el aislamiento por usuario y ensamblado en intranets, pero no en Internet. La llamada al método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> y pasar un usuario y un ensamblado <xref:System.IO.IsolatedStorage.IsolatedStorageScope> devuelven almacenamiento con este tipo de aislamiento.  
  
 El ejemplo de código siguiente recupera un almacén aislado por usuario y ensamblado. Se puede acceder al almacén con el objeto `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Para obtener un ejemplo que utiliza los parámetros de prueba, consulte <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 El método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> está disponible como un acceso directo, como se muestra en el ejemplo de código siguiente. Este acceso directo no se puede usar para abrir almacenes que son capaces de realizar la itinerancia; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> en esos casos.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>
## <a name="isolation-by-user-domain-and-assembly"></a>Aislamiento por usuario, dominio y ensamblado  
 Si la aplicación usa un ensamblado de terceros que requiera un almacén de datos privado, puede usar el almacenamiento aislado para almacenar los datos privados. El aislamiento por usuario, dominio y ensamblado garantiza que solo el código de un ensamblado determinado pueda acceder a los datos, únicamente cuando el ensamblado lo usa la aplicación que se estaba ejecutando cuando el ensamblado creó el almacén y solo cuando el usuario para el que se creó el almacén ejecuta la aplicación. El aislamiento por usuario, dominio y ensamblado impide que el ensamblado de terceros filtre datos a otras aplicaciones. Este tipo de aislamiento debe ser la opción predeterminada si sabe que desea usar el almacenamiento aislado pero no está seguro de qué tipo de aislamiento usar. La llamada al método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> y pasar un usuario, un dominio y un ensamblado <xref:System.IO.IsolatedStorage.IsolatedStorageScope> devuelven almacenamiento con este tipo de aislamiento.  
  
 El ejemplo de código siguiente recupera un almacén aislado por usuario, dominio y ensamblado. Se puede acceder al almacén con el objeto `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Otro método está disponible como acceso directo, como se muestra en el ejemplo de código siguiente. Este acceso directo no se puede usar para abrir almacenes que son capaces de realizar la itinerancia; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> en esos casos.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>
## <a name="isolated-storage-and-roaming"></a>Almacenamiento aislado e itinerancia  
 Los perfiles de usuario móvil son una característica de Windows que permite a un usuario configurar una identidad en una red y utilizar esa identidad para iniciar sesión en cualquier equipo de la red, conservando toda la configuración personalizada. Un ensamblado que usa almacenamiento aislado puede especificar que el almacenamiento aislado del usuario debe moverse con el perfil de usuario móvil. La itinerancia puede usarse junto con el aislamiento por usuario y ensamblado o con el aislamiento por usuario, dominio y ensamblado. Si no se usa un ámbito de itinerancia, los almacenes no realizarán la itinerancia aunque se use el perfil de usuario móvil.  
  
 El ejemplo de código siguiente realiza la itinerancia de un almacén aislado por usuario y ensamblado. Se puede acceder al almacén con el objeto `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Un ámbito de dominio se puede agregar para crear un almacén de itinerancia aislado por usuario, dominio y aplicación. El siguiente ejemplo de código muestra esto.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Almacenamiento aislado](isolated-storage.md)
