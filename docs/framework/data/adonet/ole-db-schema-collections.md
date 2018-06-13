---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766938"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="e52b9-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="e52b9-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="e52b9-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="e52b9-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="e52b9-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="e52b9-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="e52b9-105">El controlador OLE DB de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="e52b9-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e52b9-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="e52b9-106">Tables</span></span>  
  
-   <span data-ttu-id="e52b9-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="e52b9-107">Columns</span></span>  
  
-   <span data-ttu-id="e52b9-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e52b9-108">Procedures</span></span>  
  
-   <span data-ttu-id="e52b9-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e52b9-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e52b9-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e52b9-110">Catalog</span></span>  
  
-   <span data-ttu-id="e52b9-111">Índices</span><span class="sxs-lookup"><span data-stu-id="e52b9-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e52b9-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="e52b9-112">Tables</span></span>  
  
|<span data-ttu-id="e52b9-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-113">ColumnName</span></span>|<span data-ttu-id="e52b9-114">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-115">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-116">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-116">String</span></span>|  
|<span data-ttu-id="e52b9-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-118">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-118">String</span></span>|  
|<span data-ttu-id="e52b9-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-119">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-120">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-120">String</span></span>|  
|<span data-ttu-id="e52b9-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-121">TABLE_TYPE</span></span>|<span data-ttu-id="e52b9-122">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-122">String</span></span>|  
|<span data-ttu-id="e52b9-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-123">TABLE_GUID</span></span>|<span data-ttu-id="e52b9-124">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-124">Guid</span></span>|  
|<span data-ttu-id="e52b9-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-125">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-126">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-126">String</span></span>|  
|<span data-ttu-id="e52b9-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-127">TABLE_PROPID</span></span>|<span data-ttu-id="e52b9-128">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-128">Int64</span></span>|  
|<span data-ttu-id="e52b9-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-129">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-130">DateTime</span></span>|  
|<span data-ttu-id="e52b9-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-131">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e52b9-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="e52b9-133">Columns</span></span>  
  
|<span data-ttu-id="e52b9-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-134">ColumnName</span></span>|<span data-ttu-id="e52b9-135">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-136">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-137">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-137">String</span></span>|  
|<span data-ttu-id="e52b9-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-139">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-139">String</span></span>|  
|<span data-ttu-id="e52b9-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-140">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-141">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-141">String</span></span>|  
|<span data-ttu-id="e52b9-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-142">COLUMN_NAME</span></span>|<span data-ttu-id="e52b9-143">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-143">String</span></span>|  
|<span data-ttu-id="e52b9-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-144">COLUMN_GUID</span></span>|<span data-ttu-id="e52b9-145">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-145">Guid</span></span>|  
|<span data-ttu-id="e52b9-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-146">COLUMN_PROPID</span></span>|<span data-ttu-id="e52b9-147">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-147">Int64</span></span>|  
|<span data-ttu-id="e52b9-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-149">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-149">Int64</span></span>|  
|<span data-ttu-id="e52b9-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e52b9-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-151">Boolean</span></span>|  
|<span data-ttu-id="e52b9-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e52b9-153">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-153">String</span></span>|  
|<span data-ttu-id="e52b9-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e52b9-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="e52b9-155">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-155">Int64</span></span>|  
|<span data-ttu-id="e52b9-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e52b9-156">IS_NULLABLE</span></span>|<span data-ttu-id="e52b9-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-157">Boolean</span></span>|  
|<span data-ttu-id="e52b9-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-158">DATA_TYPE</span></span>|<span data-ttu-id="e52b9-159">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-159">Int32</span></span>|  
|<span data-ttu-id="e52b9-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-160">TYPE_GUID</span></span>|<span data-ttu-id="e52b9-161">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-161">Guid</span></span>|  
|<span data-ttu-id="e52b9-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e52b9-163">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-163">Int64</span></span>|  
|<span data-ttu-id="e52b9-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e52b9-165">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-165">Int64</span></span>|  
|<span data-ttu-id="e52b9-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e52b9-167">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-167">Int32</span></span>|  
|<span data-ttu-id="e52b9-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e52b9-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="e52b9-169">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-169">Int16</span></span>|  
|<span data-ttu-id="e52b9-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="e52b9-171">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-171">Int64</span></span>|  
|<span data-ttu-id="e52b9-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e52b9-173">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-173">String</span></span>|  
|<span data-ttu-id="e52b9-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e52b9-175">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-175">String</span></span>|  
|<span data-ttu-id="e52b9-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e52b9-177">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-177">String</span></span>|  
|<span data-ttu-id="e52b9-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="e52b9-179">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-179">String</span></span>|  
|<span data-ttu-id="e52b9-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e52b9-181">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-181">String</span></span>|  
|<span data-ttu-id="e52b9-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-182">COLLATION_NAME</span></span>|<span data-ttu-id="e52b9-183">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-183">String</span></span>|  
|<span data-ttu-id="e52b9-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e52b9-185">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-185">String</span></span>|  
|<span data-ttu-id="e52b9-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e52b9-187">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-187">String</span></span>|  
|<span data-ttu-id="e52b9-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-188">DOMAIN_NAME</span></span>|<span data-ttu-id="e52b9-189">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-189">String</span></span>|  
|<span data-ttu-id="e52b9-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-190">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-191">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-191">String</span></span>|  
|<span data-ttu-id="e52b9-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="e52b9-192">COLUMN_LCID</span></span>|<span data-ttu-id="e52b9-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-193">Int32</span></span>|  
|<span data-ttu-id="e52b9-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="e52b9-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="e52b9-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-195">Int32</span></span>|  
|<span data-ttu-id="e52b9-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="e52b9-196">COLUMN_SORTID</span></span>|<span data-ttu-id="e52b9-197">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-197">Int32</span></span>|  
|<span data-ttu-id="e52b9-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="e52b9-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="e52b9-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="e52b9-199">Byte[]</span></span>|  
|<span data-ttu-id="e52b9-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="e52b9-200">IS_COMPUTED</span></span>|<span data-ttu-id="e52b9-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e52b9-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e52b9-202">Procedures</span></span>  
  
|<span data-ttu-id="e52b9-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-203">ColumnName</span></span>|<span data-ttu-id="e52b9-204">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e52b9-206">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-206">String</span></span>|  
|<span data-ttu-id="e52b9-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e52b9-208">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-208">String</span></span>|  
|<span data-ttu-id="e52b9-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="e52b9-210">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-210">String</span></span>|  
|<span data-ttu-id="e52b9-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e52b9-212">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-212">Int16</span></span>|  
|<span data-ttu-id="e52b9-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e52b9-214">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-214">String</span></span>|  
|<span data-ttu-id="e52b9-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-215">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-216">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-216">String</span></span>|  
|<span data-ttu-id="e52b9-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-217">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-218">DateTime</span></span>|  
|<span data-ttu-id="e52b9-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-219">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e52b9-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e52b9-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e52b9-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-222">ColumnName</span></span>|<span data-ttu-id="e52b9-223">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e52b9-225">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-225">String</span></span>|  
|<span data-ttu-id="e52b9-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e52b9-227">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-227">String</span></span>|  
|<span data-ttu-id="e52b9-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="e52b9-229">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-229">String</span></span>|  
|<span data-ttu-id="e52b9-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-230">PARAMETER_NAME</span></span>|<span data-ttu-id="e52b9-231">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-231">String</span></span>|  
|<span data-ttu-id="e52b9-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-233">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-233">Int32</span></span>|  
|<span data-ttu-id="e52b9-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="e52b9-235">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-235">Int32</span></span>|  
|<span data-ttu-id="e52b9-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="e52b9-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-237">Boolean</span></span>|  
|<span data-ttu-id="e52b9-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="e52b9-239">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-239">String</span></span>|  
|<span data-ttu-id="e52b9-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e52b9-240">IS_NULLABLE</span></span>|<span data-ttu-id="e52b9-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-241">Boolean</span></span>|  
|<span data-ttu-id="e52b9-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-242">DATA_TYPE</span></span>|<span data-ttu-id="e52b9-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-243">Int32</span></span>|  
|<span data-ttu-id="e52b9-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e52b9-245">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-245">Int64</span></span>|  
|<span data-ttu-id="e52b9-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e52b9-247">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-247">Int64</span></span>|  
|<span data-ttu-id="e52b9-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e52b9-249">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-249">Int32</span></span>|  
|<span data-ttu-id="e52b9-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e52b9-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="e52b9-251">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-251">Int16</span></span>|  
|<span data-ttu-id="e52b9-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-252">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-253">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-253">String</span></span>|  
|<span data-ttu-id="e52b9-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-254">TYPE_NAME</span></span>|<span data-ttu-id="e52b9-255">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-255">String</span></span>|  
|<span data-ttu-id="e52b9-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="e52b9-257">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="e52b9-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e52b9-258">Catalog</span></span>  
  
|<span data-ttu-id="e52b9-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-259">ColumnName</span></span>|<span data-ttu-id="e52b9-260">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-261">CATALOG_NAME</span></span>|<span data-ttu-id="e52b9-262">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-262">String</span></span>|  
|<span data-ttu-id="e52b9-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-263">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-264">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e52b9-265">Índices</span><span class="sxs-lookup"><span data-stu-id="e52b9-265">Indexes</span></span>  
  
|<span data-ttu-id="e52b9-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-266">ColumnName</span></span>|<span data-ttu-id="e52b9-267">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-268">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-269">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-269">String</span></span>|  
|<span data-ttu-id="e52b9-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-271">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-271">String</span></span>|  
|<span data-ttu-id="e52b9-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-272">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-273">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-273">String</span></span>|  
|<span data-ttu-id="e52b9-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-274">INDEX_CATALOG</span></span>|<span data-ttu-id="e52b9-275">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-275">String</span></span>|  
|<span data-ttu-id="e52b9-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="e52b9-277">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-277">String</span></span>|  
|<span data-ttu-id="e52b9-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-278">INDEX_NAME</span></span>|<span data-ttu-id="e52b9-279">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-279">String</span></span>|  
|<span data-ttu-id="e52b9-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e52b9-280">PRIMARY_KEY</span></span>|<span data-ttu-id="e52b9-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-281">Boolean</span></span>|  
|<span data-ttu-id="e52b9-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e52b9-282">UNIQUE</span></span>|<span data-ttu-id="e52b9-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-283">Boolean</span></span>|  
|<span data-ttu-id="e52b9-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e52b9-284">CLUSTERED</span></span>|<span data-ttu-id="e52b9-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-285">Boolean</span></span>|  
|<span data-ttu-id="e52b9-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-286">TYPE</span></span>|<span data-ttu-id="e52b9-287">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-287">Int32</span></span>|  
|<span data-ttu-id="e52b9-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e52b9-288">FILL_FACTOR</span></span>|<span data-ttu-id="e52b9-289">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-289">Int32</span></span>|  
|<span data-ttu-id="e52b9-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e52b9-290">INITIAL_SIZE</span></span>|<span data-ttu-id="e52b9-291">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-291">Int32</span></span>|  
|<span data-ttu-id="e52b9-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="e52b9-292">NULLS</span></span>|<span data-ttu-id="e52b9-293">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-293">Int32</span></span>|  
|<span data-ttu-id="e52b9-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e52b9-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e52b9-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-295">Boolean</span></span>|  
|<span data-ttu-id="e52b9-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e52b9-296">AUTO_UPDATE</span></span>|<span data-ttu-id="e52b9-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-297">Boolean</span></span>|  
|<span data-ttu-id="e52b9-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e52b9-298">NULL_COLLATION</span></span>|<span data-ttu-id="e52b9-299">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-299">Int32</span></span>|  
|<span data-ttu-id="e52b9-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-301">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-301">Int64</span></span>|  
|<span data-ttu-id="e52b9-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-302">COLUMN_NAME</span></span>|<span data-ttu-id="e52b9-303">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-303">String</span></span>|  
|<span data-ttu-id="e52b9-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-304">COLUMN_GUID</span></span>|<span data-ttu-id="e52b9-305">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-305">Guid</span></span>|  
|<span data-ttu-id="e52b9-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-306">COLUMN_PROPID</span></span>|<span data-ttu-id="e52b9-307">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-307">Int64</span></span>|  
|<span data-ttu-id="e52b9-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e52b9-308">COLLATION</span></span>|<span data-ttu-id="e52b9-309">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-309">Int16</span></span>|  
|<span data-ttu-id="e52b9-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e52b9-310">CARDINALITY</span></span>|<span data-ttu-id="e52b9-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="e52b9-311">Decimal</span></span>|  
|<span data-ttu-id="e52b9-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="e52b9-312">PAGES</span></span>|<span data-ttu-id="e52b9-313">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-313">Int32</span></span>|  
|<span data-ttu-id="e52b9-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-314">FILTER_CONDITION</span></span>|<span data-ttu-id="e52b9-315">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-315">String</span></span>|  
|<span data-ttu-id="e52b9-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-316">INTEGRATED</span></span>|<span data-ttu-id="e52b9-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="e52b9-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="e52b9-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="e52b9-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="e52b9-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e52b9-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="e52b9-320">Tables</span></span>  
  
-   <span data-ttu-id="e52b9-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="e52b9-321">Columns</span></span>  
  
-   <span data-ttu-id="e52b9-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e52b9-322">Procedures</span></span>  
  
-   <span data-ttu-id="e52b9-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e52b9-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e52b9-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e52b9-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e52b9-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="e52b9-325">Views</span></span>  
  
-   <span data-ttu-id="e52b9-326">Índices</span><span class="sxs-lookup"><span data-stu-id="e52b9-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e52b9-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="e52b9-327">Tables</span></span>  
  
|<span data-ttu-id="e52b9-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-328">ColumnName</span></span>|<span data-ttu-id="e52b9-329">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-330">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-331">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-331">String</span></span>|  
|<span data-ttu-id="e52b9-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-333">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-333">String</span></span>|  
|<span data-ttu-id="e52b9-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-334">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-335">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-335">String</span></span>|  
|<span data-ttu-id="e52b9-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-336">TABLE_TYPE</span></span>|<span data-ttu-id="e52b9-337">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-337">String</span></span>|  
|<span data-ttu-id="e52b9-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-338">TABLE_GUID</span></span>|<span data-ttu-id="e52b9-339">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-339">Guid</span></span>|  
|<span data-ttu-id="e52b9-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-340">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-341">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-341">String</span></span>|  
|<span data-ttu-id="e52b9-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-342">TABLE_PROPID</span></span>|<span data-ttu-id="e52b9-343">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-343">Int64</span></span>|  
|<span data-ttu-id="e52b9-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-344">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-345">DateTime</span></span>|  
|<span data-ttu-id="e52b9-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-346">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e52b9-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="e52b9-348">Columns</span></span>  
  
|<span data-ttu-id="e52b9-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-349">ColumnName</span></span>|<span data-ttu-id="e52b9-350">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-351">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-352">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-352">String</span></span>|  
|<span data-ttu-id="e52b9-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-354">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-354">String</span></span>|  
|<span data-ttu-id="e52b9-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-355">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-356">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-356">String</span></span>|  
|<span data-ttu-id="e52b9-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-357">COLUMN_NAME</span></span>|<span data-ttu-id="e52b9-358">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-358">String</span></span>|  
|<span data-ttu-id="e52b9-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-359">COLUMN_GUID</span></span>|<span data-ttu-id="e52b9-360">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-360">Guid</span></span>|  
|<span data-ttu-id="e52b9-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-361">COLUMN_PROPID</span></span>|<span data-ttu-id="e52b9-362">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-362">Int64</span></span>|  
|<span data-ttu-id="e52b9-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-364">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-364">Int64</span></span>|  
|<span data-ttu-id="e52b9-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e52b9-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-366">Boolean</span></span>|  
|<span data-ttu-id="e52b9-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e52b9-368">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-368">String</span></span>|  
|<span data-ttu-id="e52b9-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e52b9-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="e52b9-370">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-370">Int64</span></span>|  
|<span data-ttu-id="e52b9-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e52b9-371">IS_NULLABLE</span></span>|<span data-ttu-id="e52b9-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-372">Boolean</span></span>|  
|<span data-ttu-id="e52b9-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-373">DATA_TYPE</span></span>|<span data-ttu-id="e52b9-374">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-374">Int32</span></span>|  
|<span data-ttu-id="e52b9-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-375">TYPE_GUID</span></span>|<span data-ttu-id="e52b9-376">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-376">Guid</span></span>|  
|<span data-ttu-id="e52b9-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e52b9-378">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-378">Int64</span></span>|  
|<span data-ttu-id="e52b9-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e52b9-380">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-380">Int64</span></span>|  
|<span data-ttu-id="e52b9-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e52b9-382">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-382">Int32</span></span>|  
|<span data-ttu-id="e52b9-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e52b9-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="e52b9-384">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-384">Int16</span></span>|  
|<span data-ttu-id="e52b9-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="e52b9-386">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-386">Int64</span></span>|  
|<span data-ttu-id="e52b9-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e52b9-388">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-388">String</span></span>|  
|<span data-ttu-id="e52b9-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e52b9-390">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-390">String</span></span>|  
|<span data-ttu-id="e52b9-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e52b9-392">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-392">String</span></span>|  
|<span data-ttu-id="e52b9-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="e52b9-394">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-394">String</span></span>|  
|<span data-ttu-id="e52b9-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e52b9-396">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-396">String</span></span>|  
|<span data-ttu-id="e52b9-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-397">COLLATION_NAME</span></span>|<span data-ttu-id="e52b9-398">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-398">String</span></span>|  
|<span data-ttu-id="e52b9-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e52b9-400">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-400">String</span></span>|  
|<span data-ttu-id="e52b9-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e52b9-402">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-402">String</span></span>|  
|<span data-ttu-id="e52b9-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-403">DOMAIN_NAME</span></span>|<span data-ttu-id="e52b9-404">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-404">String</span></span>|  
|<span data-ttu-id="e52b9-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-405">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-406">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e52b9-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e52b9-407">Procedures</span></span>  
  
|<span data-ttu-id="e52b9-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-408">ColumnName</span></span>|<span data-ttu-id="e52b9-409">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e52b9-411">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-411">String</span></span>|  
|<span data-ttu-id="e52b9-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e52b9-413">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-413">String</span></span>|  
|<span data-ttu-id="e52b9-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="e52b9-415">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-415">String</span></span>|  
|<span data-ttu-id="e52b9-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e52b9-417">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-417">Int16</span></span>|  
|<span data-ttu-id="e52b9-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e52b9-419">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-419">String</span></span>|  
|<span data-ttu-id="e52b9-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-420">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-421">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-421">String</span></span>|  
|<span data-ttu-id="e52b9-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-422">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-423">DateTime</span></span>|  
|<span data-ttu-id="e52b9-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-424">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e52b9-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e52b9-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e52b9-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-427">ColumnName</span></span>|<span data-ttu-id="e52b9-428">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e52b9-430">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-430">String</span></span>|  
|<span data-ttu-id="e52b9-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e52b9-432">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-432">String</span></span>|  
|<span data-ttu-id="e52b9-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="e52b9-434">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-434">String</span></span>|  
|<span data-ttu-id="e52b9-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-435">COLUMN_NAME</span></span>|<span data-ttu-id="e52b9-436">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-436">String</span></span>|  
|<span data-ttu-id="e52b9-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-437">COLUMN_GUID</span></span>|<span data-ttu-id="e52b9-438">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-438">Guid</span></span>|  
|<span data-ttu-id="e52b9-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-439">COLUMN_PROPID</span></span>|<span data-ttu-id="e52b9-440">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-440">Int64</span></span>|  
|<span data-ttu-id="e52b9-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="e52b9-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="e52b9-442">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-442">Int64</span></span>|  
|<span data-ttu-id="e52b9-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-444">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-444">Int64</span></span>|  
|<span data-ttu-id="e52b9-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e52b9-445">IS_NULLABLE</span></span>|<span data-ttu-id="e52b9-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-446">Boolean</span></span>|  
|<span data-ttu-id="e52b9-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-447">DATA_TYPE</span></span>|<span data-ttu-id="e52b9-448">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-448">Int32</span></span>|  
|<span data-ttu-id="e52b9-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-449">TYPE_GUID</span></span>|<span data-ttu-id="e52b9-450">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-450">Guid</span></span>|  
|<span data-ttu-id="e52b9-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e52b9-452">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-452">Int64</span></span>|  
|<span data-ttu-id="e52b9-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e52b9-454">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-454">Int64</span></span>|  
|<span data-ttu-id="e52b9-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e52b9-456">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-456">Int32</span></span>|  
|<span data-ttu-id="e52b9-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e52b9-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="e52b9-458">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-458">Int16</span></span>|  
|<span data-ttu-id="e52b9-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-459">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-460">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-460">String</span></span>|  
|<span data-ttu-id="e52b9-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e52b9-461">OVERLOAD</span></span>|<span data-ttu-id="e52b9-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e52b9-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="e52b9-463">Views</span></span>  
  
|<span data-ttu-id="e52b9-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-464">ColumnName</span></span>|<span data-ttu-id="e52b9-465">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-466">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-467">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-467">String</span></span>|  
|<span data-ttu-id="e52b9-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-469">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-469">String</span></span>|  
|<span data-ttu-id="e52b9-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-470">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-471">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-471">String</span></span>|  
|<span data-ttu-id="e52b9-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="e52b9-473">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-473">String</span></span>|  
|<span data-ttu-id="e52b9-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-474">CHECK_OPTION</span></span>|<span data-ttu-id="e52b9-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-475">Boolean</span></span>|  
|<span data-ttu-id="e52b9-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e52b9-476">IS_UPDATABLE</span></span>|<span data-ttu-id="e52b9-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-477">Boolean</span></span>|  
|<span data-ttu-id="e52b9-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-478">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-479">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-479">String</span></span>|  
|<span data-ttu-id="e52b9-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-480">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-481">DateTime</span></span>|  
|<span data-ttu-id="e52b9-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-482">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e52b9-484">Índices</span><span class="sxs-lookup"><span data-stu-id="e52b9-484">Indexes</span></span>  
  
|<span data-ttu-id="e52b9-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-485">ColumnName</span></span>|<span data-ttu-id="e52b9-486">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-487">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-488">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-488">String</span></span>|  
|<span data-ttu-id="e52b9-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-490">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-490">String</span></span>|  
|<span data-ttu-id="e52b9-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-491">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-492">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-492">String</span></span>|  
|<span data-ttu-id="e52b9-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-493">INDEX_CATALOG</span></span>|<span data-ttu-id="e52b9-494">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-494">String</span></span>|  
|<span data-ttu-id="e52b9-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="e52b9-496">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-496">String</span></span>|  
|<span data-ttu-id="e52b9-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-497">INDEX_NAME</span></span>|<span data-ttu-id="e52b9-498">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-498">String</span></span>|  
|<span data-ttu-id="e52b9-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e52b9-499">PRIMARY_KEY</span></span>|<span data-ttu-id="e52b9-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-500">Boolean</span></span>|  
|<span data-ttu-id="e52b9-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e52b9-501">UNIQUE</span></span>|<span data-ttu-id="e52b9-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-502">Boolean</span></span>|  
|<span data-ttu-id="e52b9-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e52b9-503">CLUSTERED</span></span>|<span data-ttu-id="e52b9-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-504">Boolean</span></span>|  
|<span data-ttu-id="e52b9-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-505">TYPE</span></span>|<span data-ttu-id="e52b9-506">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-506">Int32</span></span>|  
|<span data-ttu-id="e52b9-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e52b9-507">FILL_FACTOR</span></span>|<span data-ttu-id="e52b9-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-508">Int32</span></span>|  
|<span data-ttu-id="e52b9-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e52b9-509">INITIAL_SIZE</span></span>|<span data-ttu-id="e52b9-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-510">Int32</span></span>|  
|<span data-ttu-id="e52b9-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="e52b9-511">NULLS</span></span>|<span data-ttu-id="e52b9-512">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-512">Int32</span></span>|  
|<span data-ttu-id="e52b9-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e52b9-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e52b9-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-514">Boolean</span></span>|  
|<span data-ttu-id="e52b9-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e52b9-515">AUTO_UPDATE</span></span>|<span data-ttu-id="e52b9-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-516">Boolean</span></span>|  
|<span data-ttu-id="e52b9-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e52b9-517">NULL_COLLATION</span></span>|<span data-ttu-id="e52b9-518">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-518">Int32</span></span>|  
|<span data-ttu-id="e52b9-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-520">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-520">Int64</span></span>|  
|<span data-ttu-id="e52b9-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-521">COLUMN_NAME</span></span>|<span data-ttu-id="e52b9-522">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-522">String</span></span>|  
|<span data-ttu-id="e52b9-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-523">COLUMN_GUID</span></span>|<span data-ttu-id="e52b9-524">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-524">Guid</span></span>|  
|<span data-ttu-id="e52b9-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-525">COLUMN_PROPID</span></span>|<span data-ttu-id="e52b9-526">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-526">Int64</span></span>|  
|<span data-ttu-id="e52b9-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e52b9-527">COLLATION</span></span>|<span data-ttu-id="e52b9-528">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-528">Int16</span></span>|  
|<span data-ttu-id="e52b9-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e52b9-529">CARDINALITY</span></span>|<span data-ttu-id="e52b9-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="e52b9-530">Decimal</span></span>|  
|<span data-ttu-id="e52b9-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="e52b9-531">PAGES</span></span>|<span data-ttu-id="e52b9-532">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-532">Int32</span></span>|  
|<span data-ttu-id="e52b9-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-533">FILTER_CONDITION</span></span>|<span data-ttu-id="e52b9-534">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-534">String</span></span>|  
|<span data-ttu-id="e52b9-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-535">INTEGRATED</span></span>|<span data-ttu-id="e52b9-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="e52b9-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="e52b9-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="e52b9-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="e52b9-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e52b9-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="e52b9-539">Tables</span></span>  
  
-   <span data-ttu-id="e52b9-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="e52b9-540">Columns</span></span>  
  
-   <span data-ttu-id="e52b9-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e52b9-541">Procedures</span></span>  
  
-   <span data-ttu-id="e52b9-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="e52b9-542">Views</span></span>  
  
-   <span data-ttu-id="e52b9-543">Índices</span><span class="sxs-lookup"><span data-stu-id="e52b9-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e52b9-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="e52b9-544">Tables</span></span>  
  
|<span data-ttu-id="e52b9-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-545">ColumnName</span></span>|<span data-ttu-id="e52b9-546">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-547">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-548">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-548">String</span></span>|  
|<span data-ttu-id="e52b9-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-550">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-550">String</span></span>|  
|<span data-ttu-id="e52b9-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-551">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-552">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-552">String</span></span>|  
|<span data-ttu-id="e52b9-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-553">TABLE_TYPE</span></span>|<span data-ttu-id="e52b9-554">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-554">String</span></span>|  
|<span data-ttu-id="e52b9-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-555">TABLE_GUID</span></span>|<span data-ttu-id="e52b9-556">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-556">Guid</span></span>|  
|<span data-ttu-id="e52b9-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-557">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-558">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-558">String</span></span>|  
|<span data-ttu-id="e52b9-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-559">TABLE_PROPID</span></span>|<span data-ttu-id="e52b9-560">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-560">Int64</span></span>|  
|<span data-ttu-id="e52b9-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-561">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-562">DateTime</span></span>|  
|<span data-ttu-id="e52b9-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-563">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e52b9-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="e52b9-565">Columns</span></span>  
  
|<span data-ttu-id="e52b9-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-566">ColumnName</span></span>|<span data-ttu-id="e52b9-567">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-568">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-569">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-569">String</span></span>|  
|<span data-ttu-id="e52b9-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-571">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-571">String</span></span>|  
|<span data-ttu-id="e52b9-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-572">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-573">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-573">String</span></span>|  
|<span data-ttu-id="e52b9-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-574">COLUMN_NAME</span></span>|<span data-ttu-id="e52b9-575">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-575">String</span></span>|  
|<span data-ttu-id="e52b9-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-576">COLUMN_GUID</span></span>|<span data-ttu-id="e52b9-577">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-577">Guid</span></span>|  
|<span data-ttu-id="e52b9-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-578">COLUMN_PROPID</span></span>|<span data-ttu-id="e52b9-579">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-579">Int64</span></span>|  
|<span data-ttu-id="e52b9-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-581">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-581">Int64</span></span>|  
|<span data-ttu-id="e52b9-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e52b9-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-583">Boolean</span></span>|  
|<span data-ttu-id="e52b9-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e52b9-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e52b9-585">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-585">String</span></span>|  
|<span data-ttu-id="e52b9-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e52b9-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="e52b9-587">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-587">Int64</span></span>|  
|<span data-ttu-id="e52b9-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e52b9-588">IS_NULLABLE</span></span>|<span data-ttu-id="e52b9-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-589">Boolean</span></span>|  
|<span data-ttu-id="e52b9-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-590">DATA_TYPE</span></span>|<span data-ttu-id="e52b9-591">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-591">Int32</span></span>|  
|<span data-ttu-id="e52b9-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-592">TYPE_GUID</span></span>|<span data-ttu-id="e52b9-593">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-593">Guid</span></span>|  
|<span data-ttu-id="e52b9-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e52b9-595">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-595">Int64</span></span>|  
|<span data-ttu-id="e52b9-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e52b9-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e52b9-597">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-597">Int64</span></span>|  
|<span data-ttu-id="e52b9-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e52b9-599">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-599">Int32</span></span>|  
|<span data-ttu-id="e52b9-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e52b9-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="e52b9-601">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-601">Int16</span></span>|  
|<span data-ttu-id="e52b9-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e52b9-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="e52b9-603">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-603">Int64</span></span>|  
|<span data-ttu-id="e52b9-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e52b9-605">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-605">String</span></span>|  
|<span data-ttu-id="e52b9-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e52b9-607">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-607">String</span></span>|  
|<span data-ttu-id="e52b9-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e52b9-609">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-609">String</span></span>|  
|<span data-ttu-id="e52b9-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="e52b9-611">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-611">String</span></span>|  
|<span data-ttu-id="e52b9-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e52b9-613">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-613">String</span></span>|  
|<span data-ttu-id="e52b9-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-614">COLLATION_NAME</span></span>|<span data-ttu-id="e52b9-615">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-615">String</span></span>|  
|<span data-ttu-id="e52b9-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e52b9-617">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-617">String</span></span>|  
|<span data-ttu-id="e52b9-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e52b9-619">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-619">String</span></span>|  
|<span data-ttu-id="e52b9-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-620">DOMAIN_NAME</span></span>|<span data-ttu-id="e52b9-621">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-621">String</span></span>|  
|<span data-ttu-id="e52b9-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-622">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-623">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e52b9-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e52b9-624">Procedures</span></span>  
  
|<span data-ttu-id="e52b9-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-625">ColumnName</span></span>|<span data-ttu-id="e52b9-626">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e52b9-628">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-628">String</span></span>|  
|<span data-ttu-id="e52b9-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e52b9-630">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-630">String</span></span>|  
|<span data-ttu-id="e52b9-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="e52b9-632">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-632">String</span></span>|  
|<span data-ttu-id="e52b9-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e52b9-634">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-634">Int16</span></span>|  
|<span data-ttu-id="e52b9-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e52b9-636">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-636">String</span></span>|  
|<span data-ttu-id="e52b9-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-637">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-638">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-638">String</span></span>|  
|<span data-ttu-id="e52b9-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-639">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-640">DateTime</span></span>|  
|<span data-ttu-id="e52b9-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-641">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e52b9-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="e52b9-643">Views</span></span>  
  
|<span data-ttu-id="e52b9-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-644">ColumnName</span></span>|<span data-ttu-id="e52b9-645">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-646">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-647">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-647">String</span></span>|  
|<span data-ttu-id="e52b9-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-649">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-649">String</span></span>|  
|<span data-ttu-id="e52b9-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-650">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-651">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-651">String</span></span>|  
|<span data-ttu-id="e52b9-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="e52b9-653">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-653">String</span></span>|  
|<span data-ttu-id="e52b9-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-654">CHECK_OPTION</span></span>|<span data-ttu-id="e52b9-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-655">Boolean</span></span>|  
|<span data-ttu-id="e52b9-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e52b9-656">IS_UPDATABLE</span></span>|<span data-ttu-id="e52b9-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-657">Boolean</span></span>|  
|<span data-ttu-id="e52b9-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e52b9-658">DESCRIPTION</span></span>|<span data-ttu-id="e52b9-659">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-659">String</span></span>|  
|<span data-ttu-id="e52b9-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-660">DATE_CREATED</span></span>|<span data-ttu-id="e52b9-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-661">DateTime</span></span>|  
|<span data-ttu-id="e52b9-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e52b9-662">DATE_MODIFIED</span></span>|<span data-ttu-id="e52b9-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="e52b9-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e52b9-664">Índices</span><span class="sxs-lookup"><span data-stu-id="e52b9-664">Indexes</span></span>  
  
|<span data-ttu-id="e52b9-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="e52b9-665">ColumnName</span></span>|<span data-ttu-id="e52b9-666">DataType</span><span class="sxs-lookup"><span data-stu-id="e52b9-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e52b9-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-667">TABLE_CATALOG</span></span>|<span data-ttu-id="e52b9-668">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-668">String</span></span>|  
|<span data-ttu-id="e52b9-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="e52b9-670">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-670">String</span></span>|  
|<span data-ttu-id="e52b9-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-671">TABLE_NAME</span></span>|<span data-ttu-id="e52b9-672">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-672">String</span></span>|  
|<span data-ttu-id="e52b9-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e52b9-673">INDEX_CATALOG</span></span>|<span data-ttu-id="e52b9-674">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-674">String</span></span>|  
|<span data-ttu-id="e52b9-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e52b9-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="e52b9-676">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-676">String</span></span>|  
|<span data-ttu-id="e52b9-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-677">INDEX_NAME</span></span>|<span data-ttu-id="e52b9-678">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-678">String</span></span>|  
|<span data-ttu-id="e52b9-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e52b9-679">PRIMARY_KEY</span></span>|<span data-ttu-id="e52b9-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-680">Boolean</span></span>|  
|<span data-ttu-id="e52b9-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e52b9-681">UNIQUE</span></span>|<span data-ttu-id="e52b9-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-682">Boolean</span></span>|  
|<span data-ttu-id="e52b9-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e52b9-683">CLUSTERED</span></span>|<span data-ttu-id="e52b9-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-684">Boolean</span></span>|  
|<span data-ttu-id="e52b9-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="e52b9-685">TYPE</span></span>|<span data-ttu-id="e52b9-686">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-686">Int32</span></span>|  
|<span data-ttu-id="e52b9-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e52b9-687">FILL_FACTOR</span></span>|<span data-ttu-id="e52b9-688">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-688">Int32</span></span>|  
|<span data-ttu-id="e52b9-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e52b9-689">INITIAL_SIZE</span></span>|<span data-ttu-id="e52b9-690">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-690">Int32</span></span>|  
|<span data-ttu-id="e52b9-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="e52b9-691">NULLS</span></span>|<span data-ttu-id="e52b9-692">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-692">Int32</span></span>|  
|<span data-ttu-id="e52b9-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e52b9-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e52b9-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-694">Boolean</span></span>|  
|<span data-ttu-id="e52b9-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e52b9-695">AUTO_UPDATE</span></span>|<span data-ttu-id="e52b9-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="e52b9-696">Boolean</span></span>|  
|<span data-ttu-id="e52b9-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e52b9-697">NULL_COLLATION</span></span>|<span data-ttu-id="e52b9-698">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-698">Int32</span></span>|  
|<span data-ttu-id="e52b9-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="e52b9-700">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-700">Int64</span></span>|  
|<span data-ttu-id="e52b9-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e52b9-701">COLUMN_NAME</span></span>|<span data-ttu-id="e52b9-702">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-702">String</span></span>|  
|<span data-ttu-id="e52b9-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e52b9-703">COLUMN_GUID</span></span>|<span data-ttu-id="e52b9-704">Guid</span><span class="sxs-lookup"><span data-stu-id="e52b9-704">Guid</span></span>|  
|<span data-ttu-id="e52b9-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e52b9-705">COLUMN_PROPID</span></span>|<span data-ttu-id="e52b9-706">Int64</span><span class="sxs-lookup"><span data-stu-id="e52b9-706">Int64</span></span>|  
|<span data-ttu-id="e52b9-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e52b9-707">COLLATION</span></span>|<span data-ttu-id="e52b9-708">Int16</span><span class="sxs-lookup"><span data-stu-id="e52b9-708">Int16</span></span>|  
|<span data-ttu-id="e52b9-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e52b9-709">CARDINALITY</span></span>|<span data-ttu-id="e52b9-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="e52b9-710">Decimal</span></span>|  
|<span data-ttu-id="e52b9-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="e52b9-711">PAGES</span></span>|<span data-ttu-id="e52b9-712">Int32</span><span class="sxs-lookup"><span data-stu-id="e52b9-712">Int32</span></span>|  
|<span data-ttu-id="e52b9-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e52b9-713">FILTER_CONDITION</span></span>|<span data-ttu-id="e52b9-714">String</span><span class="sxs-lookup"><span data-stu-id="e52b9-714">String</span></span>|  
|<span data-ttu-id="e52b9-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e52b9-715">INTEGRATED</span></span>|<span data-ttu-id="e52b9-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="e52b9-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e52b9-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="e52b9-717">See Also</span></span>  
 [<span data-ttu-id="e52b9-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="e52b9-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
