---
description: 'Más información acerca de: Procedimiento: para asignar la información de usuario para agrupar conexiones'
title: 'Cómo: asignar la información de usuario para agrupar conexiones'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ce550d6-8f7c-4ea7-add8-5bc27a7b51be
ms.openlocfilehash: 2af901b91c561f5f46c63ed627cbd0053d30e624
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729268"
---
# <a name="how-to-assign-user-information-to-group-connections"></a><span data-ttu-id="553e4-103">Procedimiento para asignar la información de usuario para agrupar conexiones</span><span class="sxs-lookup"><span data-stu-id="553e4-103">How to: Assign User Information to Group Connections</span></span>

 <span data-ttu-id="553e4-104">En el ejemplo siguiente se muestra cómo asignar la información del usuario para agrupar las conexiones, presuponiendo que la aplicación establece las variables *UserName*, *SecurelyStoredPassword* y *Domain* antes de que se llame a esta sección del código y que *UserName* es único.</span><span class="sxs-lookup"><span data-stu-id="553e4-104">The following example demonstrates how to assign user information to group connections, assuming that the application sets the variables *UserName*, *SecurelyStoredPassword*, and *Domain* before this section of code is called and that *UserName* is unique.</span></span>  
  
### <a name="to-assign-user-information-to-a-group-connection"></a><span data-ttu-id="553e4-105">Para asignar la información del usuario a una conexión de grupo</span><span class="sxs-lookup"><span data-stu-id="553e4-105">To assign user information to a group connection</span></span>  
  
1. <span data-ttu-id="553e4-106">Cree un nombre de grupo de conexión.</span><span class="sxs-lookup"><span data-stu-id="553e4-106">Create a connection group name.</span></span>  
  
    ```csharp  
    SHA1Managed Sha1 = new SHA1Managed();  
    Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
    String secureGroupName = Encoding.Default.GetString(updHash);  
    ```  
  
    ```vb  
    Dim Sha1 As New SHA1Managed()  
    Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
    Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
    ```  
  
2. <span data-ttu-id="553e4-107">Cree una solicitud de una dirección URL determinada.</span><span class="sxs-lookup"><span data-stu-id="553e4-107">Create a request for a specific URL.</span></span> <span data-ttu-id="553e4-108">Por ejemplo, el siguiente código crea una solicitud para la dirección URL `http://www.contoso.com.`.</span><span class="sxs-lookup"><span data-stu-id="553e4-108">For example, the following code creates a request for the URL `http://www.contoso.com.`</span></span>  
  
    ```csharp  
    WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
    ```  
  
    ```vb  
    Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ```  
  
3. <span data-ttu-id="553e4-109">Establezca las credenciales y la conexión GroupName para la solicitud web, y llame a **GetResponse** para recuperar un objeto **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="553e4-109">Set the credentials and Connection GroupName for the Web request, and call **GetResponse** to retrieve a **WebResponse** object.</span></span>  
  
    ```csharp  
    myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);
    myWebRequest.ConnectionGroupName = secureGroupName;  
  
    WebResponse myWebResponse=myWebRequest.GetResponse();  
    ```  
  
    ```vb  
    myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
    myWebRequest.ConnectionGroupName = secureGroupName  
  
    Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
    ```  
  
4. <span data-ttu-id="553e4-110">Cierre la secuencia de respuesta después de usar el objeto WebResponse.</span><span class="sxs-lookup"><span data-stu-id="553e4-110">Close the response stream after using the WebRespose object.</span></span>  
  
    ```csharp  
    MyWebResponse.Close();  
    ```  
  
    ```vb  
    MyWebResponse.Close()  
    ```  
  
 <span data-ttu-id="553e4-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="553e4-111">Example</span></span>  
  
```csharp  
// Create a connection group name.  
SHA1Managed Sha1 = new SHA1Managed();  
Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
String secureGroupName = Encoding.Default.GetString(updHash);  
  
// Create a request for a specific URL.  
WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
  
myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);
myWebRequest.ConnectionGroupName = secureGroupName;  
  
WebResponse myWebResponse=myWebRequest.GetResponse();  
  
// Insert the code that uses myWebResponse.  
  
MyWebResponse.Close();  
```  
  
```vb  
' Create a secure group name.  
Dim Sha1 As New SHA1Managed()  
Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
  
' Create a request for a specific URL.  
Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
  
myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
myWebRequest.ConnectionGroupName = secureGroupName  
  
Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
  
' Insert the code that uses myWebResponse.  
MyWebResponse.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="553e4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="553e4-112">See also</span></span>

- [<span data-ttu-id="553e4-113">Administrar conexiones</span><span class="sxs-lookup"><span data-stu-id="553e4-113">Managing Connections</span></span>](managing-connections.md)
- [<span data-ttu-id="553e4-114">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="553e4-114">Connection Grouping</span></span>](connection-grouping.md)
