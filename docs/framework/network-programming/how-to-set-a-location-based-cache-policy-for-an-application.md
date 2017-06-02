---
title: "C&#243;mo establecer en una aplicaci&#243;n una directiva de cach&#233; basada en la ubicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "información acerca del comportamiento del caché de definición"
  - "directivas de caché basadas en la ubicación"
  - "caché local"
  - "solicitar directivas de caché"
  - "caché [.NET Framework], directivas basadas en la ubicación"
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# C&#243;mo establecer en una aplicaci&#243;n una directiva de cach&#233; basada en la ubicaci&#243;n
Las directivas Ubicación\- basadas de caché permiten una aplicación para definir explícitamente almacenar en memoria caché el comportamiento según la ubicación del recurso solicitado.  Este tema muestra cómo establecer la directiva de caché mediante programación.  Para obtener información sobre cómo establecer la directiva para una aplicación mediante los archivos de configuración, vea [\<requestCaching\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### Para establecer una directiva ubicación\- basada en caché para una aplicación  
  
1.  Cree un objeto de <xref:System.Net.Cache.RequestCachePolicy> o de <xref:System.Net.Cache.HttpRequestCachePolicy> .  
  
2.  Establezca el objeto de directiva como valor predeterminado para el dominio de aplicación.  
  
### Para establecer una directiva que toma los recursos solicitados de caché  
  
-   Cree una directiva que toma los recursos solicitados de caché si está disponible, y otra manera, envía solicitudes al servidor, estableciendo caché nivel a <xref:System.Net.Cache.HttpRequestCacheLevel>.  Una solicitud se puede satisfacer mediante cualquier caché entre el cliente y el servidor, incluidas las memorias caché remotas.  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Para establecer una directiva que evita que cualquier caché proporcione recursos  
  
-   Cree una directiva que impida que cualquier caché proporcione recursos solicitados estableciendo caché nivel a <xref:System.Net.Cache.HttpRequestCacheLevel>.  Este nivel de directiva quita el recurso de la memoria caché local si está presente e indica a memorias caché remotas que también quitar el recurso.  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Para establecer una directiva que devuelve los recursos solicitados sólo si se encuentran en la memoria caché local  
  
-   Cree una directiva que devuelve los recursos solicitados sólo si se encuentran en la memoria caché local estableciendo caché nivel a <xref:System.Net.Cache.HttpRequestCacheLevel>.  Si el recurso solicitado no está en la caché, se produce una excepción de <xref:System.Net.WebException> .  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Para establecer una directiva que impide la caché local proporcione recursos  
  
-   Cree una directiva que impida la caché local proporcione recursos solicitados estableciendo caché nivel a <xref:System.Net.Cache.HttpRequestCacheLevel>.  Si el recurso solicitado está en caché intermedia y volverá a correctamente, la memoria caché intermedia puede proporcionar el recurso solicitado.  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Para establecer una directiva que evita que cualquier caché proporcione recursos solicitados  
  
-   Cree una directiva que impida que cualquier caché proporcione recursos solicitados estableciendo caché nivel a <xref:System.Net.Cache.HttpRequestCacheLevel>.  El recurso devuelto por el servidor puede almacenar en memoria caché.  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Para establecer una directiva que permite que cualquier caché proporcione recursos solicitados si el recurso del servidor no es más reciente que la copia en caché  
  
-   Cree una directiva que permite que cualquier caché proporcione recursos solicitados si el recurso del servidor no es más reciente que la copia en caché estableciendo caché nivel a <xref:System.Net.Cache.HttpRequestCacheLevel>.  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)   
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)