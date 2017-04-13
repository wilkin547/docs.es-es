---
title: "Tipos de aislamiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "almacenar datos mediante almacenamiento aislado, acceso al almacenamiento aislado"
  - "almacenar datos mediante almacenamiento aislado, tipos de aislamiento"
  - "autenticación [.NET Framework], almacenamiento aislado"
  - "ensamblados [.NET Framework], identidad"
  - "almacenamiento aislado, acceso"
  - "almacenamiento de datos mediante almacenamiento aislado, tipos de aislamiento"
  - "almacenamiento de datos mediante almacenamiento aislado, acceso al almacenamiento aislado"
  - "identidad de dominio"
  - "almacenamiento aislado, tipos"
  - "autenticación de usuario, almacenamiento aislado"
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Tipos de aislamiento
El acceso al almacenamiento aislado se restringe siempre al usuario que lo creó.  Para implementar este tipo de aislamiento, Common Language Runtime usa el mismo concepto de identidad de usuario que reconoce el sistema operativo, es decir, la identidad asociada al proceso en que se está ejecutando código cuando se abre el almacén.  Esta identidad es una identidad de usuario autenticada, pero la suplantación puede hacer que la identidad del usuario actual cambie dinámicamente.  
  
 El acceso al almacenamiento aislado también se restringe por la identidad asociada al dominio de la aplicación y al ensamblado, o por la del ensamblado sólo.  El motor en tiempo de ejecución obtiene estas tres identidades de las siguientes maneras:  
  
-   La identidad de dominio representa la prueba de la aplicación, que en el caso de una aplicación web podría ser la dirección URL completa.  Para código hospedado en el shell, la identidad de dominio se debe basar en la ruta de acceso del directorio de la aplicación.  Por ejemplo, si el archivo ejecutable se ejecuta desde C:\\Office\\MyApp.exe, la identidad de dominio sería C:\\Office\\MyApp.exe.  
  
-   La identidad de ensamblado es la prueba del ensamblado.  Puede proceder de una firma digital criptográfica, que puede ser el [nombre seguro](../../../docs/framework/app-domains/strong-named-assemblies.md) del ensamblado, la compañía de software del ensamblado o su identidad de dirección URL.  Si un ensamblado tiene un nombre seguro y una identidad de compañía de software, se usa ésta última.  Si el ensamblado procede de Internet y no está firmado, se usa la identidad de dirección URL.  Para obtener más información sobre ensamblados y nombres seguros, vea [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md).  
  
-   Los almacenes móviles se trasladan con un usuario que tenga un perfil de usuario móvil.  Los archivos se escriben en un directorio de red y se descargan en cualquier equipo en que el usuario inicie la sesión.  Para obtener más información sobre los perfiles de usuario móvil, vea <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName>.  
  
 Combinando los conceptos de usuario, dominio e identidad de ensamblado, el almacenamiento aislado puede aislar datos de las maneras siguientes, cada una de las cuales tiene sus propios escenarios de uso:  
  
-   [Aislamiento por usuario y ensamblado](#UserAssembly)  
  
-   [Aislamiento por el usuario, el dominio y el ensamblado](#UserDomainAssembly)  
  
 Cualquiera de estos aislamientos se puede combinar con un perfil de usuario móvil.  Para obtener más información, consulte la sección [Almacenamiento aislado y Movilidad](#Roaming).  
  
 En la siguiente ilustración se muestra cómo se aíslan los almacenes en distintos ámbitos.  
  
 ![Aislamiento por usuario y ensamblado](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
Tipos de almacenamiento aislado  
  
 Hay que tener en cuenta que excepto para los almacenes móviles, el equipo aísla siempre de manera implícita el almacenamiento aislado porque utiliza el almacenamiento local de un equipo determinado.  
  
> [!IMPORTANT]
>  El almacenamiento aislado no está disponible para las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  En su lugar, se pueden usar las clases de datos de la aplicación del espacio de nombres `Windows.Storage` incluidas en la API de [!INCLUDE[wrt](../../../includes/wrt-md.md)] para almacenar archivos y datos locales.  Para obtener más información, vea [Acceder a datos de aplicaciones con Windows en tiempo de ejecución](http://go.microsoft.com/fwlink/?LinkId=229175) en el Centro de desarrollo de Windows.  
  
<a name="UserAssembly"></a>   
## Aislamiento por usuario y por ensamblado  
 Cuando el ensamblado que utiliza el almacén de datos deba estar accesible desde el dominio de cualquier aplicación, el aislamiento por usuario y por ensamblado es adecuado.  Normalmente, en esta situación, el almacenamiento aislado se usa para guardar datos que afectan a varias aplicaciones y no están unidos a ninguna en concreto, como el nombre del usuario o la información de licencia.  Para tener acceso a almacenamiento aislado por usuario y ensamblado, el código debe ser de confianza para que transfiera información entre las aplicaciones.  Por lo general, el aislamiento por usuario y ensamblado se permite en intranets, pero no en Internet.  Si se llama al método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=fullName> de <xref:System.IO.IsolatedStorage.IsolatedStorageScope> y se pasa un usuario y un ensamblado, se obtiene el almacenamiento con este tipo de aislamiento.  
  
 El siguiente ejemplo de código recupera un almacén aislado por usuario y ensamblado.  Se puede obtener acceso al almacén mediante el objeto `isoFile` .  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Para obtener un ejemplo sobre el uso de parámetros de prueba, consulte <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 También se puede utilizar el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> como método abreviado, tal como se muestra en el ejemplo de código siguiente.  Este método abreviado no se puede usar para abrir almacenes móviles; en estos casos, use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## Aislamiento por usuario, dominio y ensamblado  
 Si la aplicación usa un ensamblado de terceros que requiere un almacén de datos privado, se puede utilizar el almacenamiento aislado para guardar los datos privados.  El aislamiento por usuario, dominio y ensamblado garantiza que sólo el código de un determinado ensamblado pueda tener acceso a los datos, sólo cuando el ensamblado esté siendo utilizado por la aplicación que se estaba ejecutando en el momento en que el ensamblado creó el almacén, y sólo cuando quien ejecuta la aplicación es el usuario para el que se creó el almacén.  El aislamiento por usuario, dominio y ensamblado impide que un ensamblado de terceros filtre datos a otras aplicaciones.  Este tipo de aislamiento se debe usar como predeterminado si se desea usar almacenamiento aislado pero no se está seguro de qué tipo de aislamiento usar.  Si se llama al método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> y se pasa un usuario, dominio y ensamblado, <xref:System.IO.IsolatedStorage.IsolatedStorageScope> devuelve un almacenamiento con este tipo de aislamiento.  
  
 El siguiente ejemplo de código recupera un almacén aislado por usuario, dominio y ensamblado.  Se puede obtener acceso al almacén mediante el objeto `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Existe otro método abreviado que también se puede usar, tal como se muestra en el ejemplo de código siguiente.  Pero no se puede usar para abrir almacenes móviles; en estos casos, use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## Aislamiento aislado y movilidad  
 Los perfiles de usuario móvil son una característica de Windows que permite que un usuario configure una identidad en una red y utilizar esa identidad para registrarse en cualquier equipo de red, transportando todas las configuraciones personalizadas.  Un ensamblado que usa almacenamiento aislado puede especificar que el almacenamiento aislado del usuario se traslade junto al perfil del usuario móvil.  La movilidad se puede usar junto con el aislamiento por usuario y ensamblado o el aislamiento por usuario, dominio y ensamblado.  Si no se usa el ámbito de la movilidad, los almacenes no se trasladarán aunque se use un perfil de usuario móvil.  
  
 El siguiente ejemplo de código recupera un almacén aislado por usuario y ensamblado móvil.  Se puede obtener acceso al almacén mediante el objeto `isoFile` .  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Se puede agregar un ámbito de dominio para crear un almacén aislado por usuario, dominio y aplicación móvil.  En el siguiente ejemplo de código se muestra este caso.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)