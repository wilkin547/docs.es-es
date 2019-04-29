---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772052"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="4c644-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="4c644-102">ODBC Schema Collections</span></span>

<span data-ttu-id="4c644-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="4c644-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="4c644-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c644-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="4c644-105">El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="4c644-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="4c644-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="4c644-106">Tables</span></span>

- <span data-ttu-id="4c644-107">Índices</span><span class="sxs-lookup"><span data-stu-id="4c644-107">Indexes</span></span>

- <span data-ttu-id="4c644-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="4c644-108">Columns</span></span>

- <span data-ttu-id="4c644-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4c644-109">Procedures</span></span>

- <span data-ttu-id="4c644-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4c644-110">ProcedureColumns</span></span>

- <span data-ttu-id="4c644-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4c644-111">ProcedureParameters</span></span>

- <span data-ttu-id="4c644-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="4c644-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="4c644-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="4c644-113">Tables and Views</span></span>

|<span data-ttu-id="4c644-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-114">ColumnName</span></span>|<span data-ttu-id="4c644-115">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="4c644-116">TABLE_CAT</span></span>|<span data-ttu-id="4c644-117">String</span><span class="sxs-lookup"><span data-stu-id="4c644-117">String</span></span>|
|<span data-ttu-id="4c644-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4c644-118">TABLE_SCHEM</span></span>|<span data-ttu-id="4c644-119">String</span><span class="sxs-lookup"><span data-stu-id="4c644-119">String</span></span>|
|<span data-ttu-id="4c644-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-120">TABLE_NAME</span></span>|<span data-ttu-id="4c644-121">String</span><span class="sxs-lookup"><span data-stu-id="4c644-121">String</span></span>|
|<span data-ttu-id="4c644-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-122">TABLE_TYPE</span></span>|<span data-ttu-id="4c644-123">String</span><span class="sxs-lookup"><span data-stu-id="4c644-123">String</span></span>|
|<span data-ttu-id="4c644-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-124">REMARKS</span></span>|<span data-ttu-id="4c644-125">String</span><span class="sxs-lookup"><span data-stu-id="4c644-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="4c644-126">Índices</span><span class="sxs-lookup"><span data-stu-id="4c644-126">Indexes</span></span>

|<span data-ttu-id="4c644-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-127">ColumnName</span></span>|<span data-ttu-id="4c644-128">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="4c644-129">TABLE_CAT</span></span>|<span data-ttu-id="4c644-130">String</span><span class="sxs-lookup"><span data-stu-id="4c644-130">String</span></span>|
|<span data-ttu-id="4c644-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4c644-131">TABLE_SCHEM</span></span>|<span data-ttu-id="4c644-132">String</span><span class="sxs-lookup"><span data-stu-id="4c644-132">String</span></span>|
|<span data-ttu-id="4c644-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-133">TABLE_NAME</span></span>|<span data-ttu-id="4c644-134">String</span><span class="sxs-lookup"><span data-stu-id="4c644-134">String</span></span>|
|<span data-ttu-id="4c644-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="4c644-135">NON_UNIQUE</span></span>|<span data-ttu-id="4c644-136">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-136">Int16</span></span>|
|<span data-ttu-id="4c644-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="4c644-138">String</span><span class="sxs-lookup"><span data-stu-id="4c644-138">String</span></span>|
|<span data-ttu-id="4c644-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-139">INDEX_NAME</span></span>|<span data-ttu-id="4c644-140">String</span><span class="sxs-lookup"><span data-stu-id="4c644-140">String</span></span>|
|<span data-ttu-id="4c644-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-141">TYPE</span></span>|<span data-ttu-id="4c644-142">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-142">Int16</span></span>|
|<span data-ttu-id="4c644-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-144">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-144">Int16</span></span>|
|<span data-ttu-id="4c644-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-145">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-146">String</span><span class="sxs-lookup"><span data-stu-id="4c644-146">String</span></span>|
|<span data-ttu-id="4c644-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="4c644-147">ASC_OR_DESC</span></span>|<span data-ttu-id="4c644-148">String</span><span class="sxs-lookup"><span data-stu-id="4c644-148">String</span></span>|
|<span data-ttu-id="4c644-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="4c644-149">CARDINALITY</span></span>|<span data-ttu-id="4c644-150">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-150">Int32</span></span>|
|<span data-ttu-id="4c644-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="4c644-151">PAGES</span></span>|<span data-ttu-id="4c644-152">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-152">Int32</span></span>|
|<span data-ttu-id="4c644-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="4c644-153">FILTER_CONDITION</span></span>|<span data-ttu-id="4c644-154">String</span><span class="sxs-lookup"><span data-stu-id="4c644-154">String</span></span>|
|<span data-ttu-id="4c644-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4c644-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4c644-156">String</span><span class="sxs-lookup"><span data-stu-id="4c644-156">String</span></span>|
|<span data-ttu-id="4c644-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="4c644-158">Byte</span><span class="sxs-lookup"><span data-stu-id="4c644-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="4c644-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="4c644-159">Columns</span></span>

|<span data-ttu-id="4c644-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-160">ColumnName</span></span>|<span data-ttu-id="4c644-161">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="4c644-162">TABLE_CAT</span></span>|<span data-ttu-id="4c644-163">String</span><span class="sxs-lookup"><span data-stu-id="4c644-163">String</span></span>|
|<span data-ttu-id="4c644-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4c644-164">TABLE_SCHEM</span></span>|<span data-ttu-id="4c644-165">String</span><span class="sxs-lookup"><span data-stu-id="4c644-165">String</span></span>|
|<span data-ttu-id="4c644-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-166">TABLE_NAME</span></span>|<span data-ttu-id="4c644-167">String</span><span class="sxs-lookup"><span data-stu-id="4c644-167">String</span></span>|
|<span data-ttu-id="4c644-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-168">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-169">String</span><span class="sxs-lookup"><span data-stu-id="4c644-169">String</span></span>|
|<span data-ttu-id="4c644-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-170">DATA_TYPE</span></span>|<span data-ttu-id="4c644-171">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-171">Int16</span></span>|
|<span data-ttu-id="4c644-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-172">TYPE_NAME</span></span>|<span data-ttu-id="4c644-173">String</span><span class="sxs-lookup"><span data-stu-id="4c644-173">String</span></span>|
|<span data-ttu-id="4c644-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4c644-174">COLUMN_SIZE</span></span>|<span data-ttu-id="4c644-175">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-175">Int32</span></span>|
|<span data-ttu-id="4c644-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="4c644-177">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-177">Int32</span></span>|
|<span data-ttu-id="4c644-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4c644-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4c644-179">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-179">Int16</span></span>|
|<span data-ttu-id="4c644-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4c644-181">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-181">Int16</span></span>|
|<span data-ttu-id="4c644-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-182">NULLABLE</span></span>|<span data-ttu-id="4c644-183">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-183">Int16</span></span>|
|<span data-ttu-id="4c644-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-184">REMARKS</span></span>|<span data-ttu-id="4c644-185">String</span><span class="sxs-lookup"><span data-stu-id="4c644-185">String</span></span>|
|<span data-ttu-id="4c644-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4c644-186">COLUMN_DEF</span></span>|<span data-ttu-id="4c644-187">String</span><span class="sxs-lookup"><span data-stu-id="4c644-187">String</span></span>|
|<span data-ttu-id="4c644-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4c644-189">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-189">Int16</span></span>|
|<span data-ttu-id="4c644-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4c644-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4c644-191">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-191">Int16</span></span>|
|<span data-ttu-id="4c644-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4c644-193">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-193">Int32</span></span>|
|<span data-ttu-id="4c644-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-195">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-195">Int32</span></span>|
|<span data-ttu-id="4c644-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-196">IS_NULLABLE</span></span>|<span data-ttu-id="4c644-197">String</span><span class="sxs-lookup"><span data-stu-id="4c644-197">String</span></span>|
|<span data-ttu-id="4c644-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4c644-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="4c644-199">String</span><span class="sxs-lookup"><span data-stu-id="4c644-199">String</span></span>|
|<span data-ttu-id="4c644-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4c644-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4c644-201">String</span><span class="sxs-lookup"><span data-stu-id="4c644-201">String</span></span>|
|<span data-ttu-id="4c644-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="4c644-203">Byte</span><span class="sxs-lookup"><span data-stu-id="4c644-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="4c644-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4c644-204">Procedures</span></span>

|<span data-ttu-id="4c644-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-205">ColumnName</span></span>|<span data-ttu-id="4c644-206">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4c644-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="4c644-208">String</span><span class="sxs-lookup"><span data-stu-id="4c644-208">String</span></span>|
|<span data-ttu-id="4c644-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4c644-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4c644-210">String</span><span class="sxs-lookup"><span data-stu-id="4c644-210">String</span></span>|
|<span data-ttu-id="4c644-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-212">String</span><span class="sxs-lookup"><span data-stu-id="4c644-212">String</span></span>|
|<span data-ttu-id="4c644-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4c644-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="4c644-214">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-214">Int32</span></span>|
|<span data-ttu-id="4c644-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4c644-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="4c644-216">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-216">Int32</span></span>|
|<span data-ttu-id="4c644-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="4c644-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="4c644-218">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-218">Int32</span></span>|
|<span data-ttu-id="4c644-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-219">REMARKS</span></span>|<span data-ttu-id="4c644-220">String</span><span class="sxs-lookup"><span data-stu-id="4c644-220">String</span></span>|
|<span data-ttu-id="4c644-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4c644-222">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="4c644-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4c644-223">ProcedureColumns</span></span>

|<span data-ttu-id="4c644-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-224">ColumnName</span></span>|<span data-ttu-id="4c644-225">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4c644-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="4c644-227">String</span><span class="sxs-lookup"><span data-stu-id="4c644-227">String</span></span>|
|<span data-ttu-id="4c644-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4c644-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4c644-229">String</span><span class="sxs-lookup"><span data-stu-id="4c644-229">String</span></span>|
|<span data-ttu-id="4c644-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-231">String</span><span class="sxs-lookup"><span data-stu-id="4c644-231">String</span></span>|
|<span data-ttu-id="4c644-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-232">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-233">String</span><span class="sxs-lookup"><span data-stu-id="4c644-233">String</span></span>|
|<span data-ttu-id="4c644-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-234">COLUMN_TYPE</span></span>|<span data-ttu-id="4c644-235">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-235">Int16</span></span>|
|<span data-ttu-id="4c644-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-236">DATA_TYPE</span></span>|<span data-ttu-id="4c644-237">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-237">Int16</span></span>|
|<span data-ttu-id="4c644-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-238">TYPE_NAME</span></span>|<span data-ttu-id="4c644-239">String</span><span class="sxs-lookup"><span data-stu-id="4c644-239">String</span></span>|
|<span data-ttu-id="4c644-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4c644-240">COLUMN_SIZE</span></span>|<span data-ttu-id="4c644-241">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-241">Int32</span></span>|
|<span data-ttu-id="4c644-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="4c644-243">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-243">Int32</span></span>|
|<span data-ttu-id="4c644-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4c644-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4c644-245">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-245">Int16</span></span>|
|<span data-ttu-id="4c644-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4c644-247">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-247">Int16</span></span>|
|<span data-ttu-id="4c644-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-248">NULLABLE</span></span>|<span data-ttu-id="4c644-249">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-249">Int16</span></span>|
|<span data-ttu-id="4c644-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-250">REMARKS</span></span>|<span data-ttu-id="4c644-251">String</span><span class="sxs-lookup"><span data-stu-id="4c644-251">String</span></span>|
|<span data-ttu-id="4c644-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4c644-252">COLUMN_DEF</span></span>|<span data-ttu-id="4c644-253">String</span><span class="sxs-lookup"><span data-stu-id="4c644-253">String</span></span>|
|<span data-ttu-id="4c644-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4c644-255">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-255">Int16</span></span>|
|<span data-ttu-id="4c644-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4c644-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4c644-257">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-257">Int16</span></span>|
|<span data-ttu-id="4c644-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4c644-259">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-259">Int32</span></span>|
|<span data-ttu-id="4c644-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-261">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-261">Int32</span></span>|
|<span data-ttu-id="4c644-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-262">IS_NULLABLE</span></span>|<span data-ttu-id="4c644-263">String</span><span class="sxs-lookup"><span data-stu-id="4c644-263">String</span></span>|
|<span data-ttu-id="4c644-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4c644-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="4c644-265">String</span><span class="sxs-lookup"><span data-stu-id="4c644-265">String</span></span>|
|<span data-ttu-id="4c644-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4c644-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4c644-267">String</span><span class="sxs-lookup"><span data-stu-id="4c644-267">String</span></span>|
|<span data-ttu-id="4c644-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="4c644-269">Byte</span><span class="sxs-lookup"><span data-stu-id="4c644-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="4c644-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4c644-270">ProcedureParameters</span></span>

|<span data-ttu-id="4c644-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-271">ColumnName</span></span>|<span data-ttu-id="4c644-272">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4c644-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="4c644-274">String</span><span class="sxs-lookup"><span data-stu-id="4c644-274">String</span></span>|
|<span data-ttu-id="4c644-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4c644-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4c644-276">String</span><span class="sxs-lookup"><span data-stu-id="4c644-276">String</span></span>|
|<span data-ttu-id="4c644-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-278">String</span><span class="sxs-lookup"><span data-stu-id="4c644-278">String</span></span>|
|<span data-ttu-id="4c644-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-279">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-280">String</span><span class="sxs-lookup"><span data-stu-id="4c644-280">String</span></span>|
|<span data-ttu-id="4c644-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-281">COLUMN_TYPE</span></span>|<span data-ttu-id="4c644-282">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-282">Int16</span></span>|
|<span data-ttu-id="4c644-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-283">DATA_TYPE</span></span>|<span data-ttu-id="4c644-284">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-284">Int16</span></span>|
|<span data-ttu-id="4c644-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-285">TYPE_NAME</span></span>|<span data-ttu-id="4c644-286">String</span><span class="sxs-lookup"><span data-stu-id="4c644-286">String</span></span>|
|<span data-ttu-id="4c644-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4c644-287">COLUMN_SIZE</span></span>|<span data-ttu-id="4c644-288">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-288">Int32</span></span>|
|<span data-ttu-id="4c644-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="4c644-290">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-290">Int32</span></span>|
|<span data-ttu-id="4c644-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4c644-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4c644-292">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-292">Int16</span></span>|
|<span data-ttu-id="4c644-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4c644-294">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-294">Int16</span></span>|
|<span data-ttu-id="4c644-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-295">NULLABLE</span></span>|<span data-ttu-id="4c644-296">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-296">Int16</span></span>|
|<span data-ttu-id="4c644-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-297">REMARKS</span></span>|<span data-ttu-id="4c644-298">String</span><span class="sxs-lookup"><span data-stu-id="4c644-298">String</span></span>|
|<span data-ttu-id="4c644-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4c644-299">COLUMN_DEF</span></span>|<span data-ttu-id="4c644-300">String</span><span class="sxs-lookup"><span data-stu-id="4c644-300">String</span></span>|
|<span data-ttu-id="4c644-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4c644-302">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-302">Int16</span></span>|
|<span data-ttu-id="4c644-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4c644-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4c644-304">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-304">Int16</span></span>|
|<span data-ttu-id="4c644-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4c644-306">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-306">Int32</span></span>|
|<span data-ttu-id="4c644-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-308">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-308">Int32</span></span>|
|<span data-ttu-id="4c644-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-309">IS_NULLABLE</span></span>|<span data-ttu-id="4c644-310">String</span><span class="sxs-lookup"><span data-stu-id="4c644-310">String</span></span>|
|<span data-ttu-id="4c644-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4c644-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="4c644-312">String</span><span class="sxs-lookup"><span data-stu-id="4c644-312">String</span></span>|
|<span data-ttu-id="4c644-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4c644-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="4c644-314">String</span><span class="sxs-lookup"><span data-stu-id="4c644-314">String</span></span>|
|<span data-ttu-id="4c644-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="4c644-316">Byte</span><span class="sxs-lookup"><span data-stu-id="4c644-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="4c644-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4c644-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="4c644-318">El controlador ODBC de Oracle de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="4c644-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="4c644-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="4c644-319">Tables</span></span>

- <span data-ttu-id="4c644-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="4c644-320">Columns</span></span>

- <span data-ttu-id="4c644-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4c644-321">Procedures</span></span>

- <span data-ttu-id="4c644-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4c644-322">ProcedureColumns</span></span>

- <span data-ttu-id="4c644-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4c644-323">ProcedureParameters</span></span>

- <span data-ttu-id="4c644-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="4c644-324">Views</span></span>

- <span data-ttu-id="4c644-325">Índices</span><span class="sxs-lookup"><span data-stu-id="4c644-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="4c644-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="4c644-326">Tables and Views</span></span>

|<span data-ttu-id="4c644-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-327">ColumnName</span></span>|<span data-ttu-id="4c644-328">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4c644-330">String</span><span class="sxs-lookup"><span data-stu-id="4c644-330">String</span></span>|
|<span data-ttu-id="4c644-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-331">TABLE_OWNER</span></span>|<span data-ttu-id="4c644-332">String</span><span class="sxs-lookup"><span data-stu-id="4c644-332">String</span></span>|
|<span data-ttu-id="4c644-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-333">TABLE_NAME</span></span>|<span data-ttu-id="4c644-334">String</span><span class="sxs-lookup"><span data-stu-id="4c644-334">String</span></span>|
|<span data-ttu-id="4c644-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-335">TABLE_TYPE</span></span>|<span data-ttu-id="4c644-336">String</span><span class="sxs-lookup"><span data-stu-id="4c644-336">String</span></span>|
|<span data-ttu-id="4c644-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-337">REMARKS</span></span>|<span data-ttu-id="4c644-338">String</span><span class="sxs-lookup"><span data-stu-id="4c644-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="4c644-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="4c644-339">Columns</span></span>

|<span data-ttu-id="4c644-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-340">ColumnName</span></span>|<span data-ttu-id="4c644-341">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4c644-343">String</span><span class="sxs-lookup"><span data-stu-id="4c644-343">String</span></span>|
|<span data-ttu-id="4c644-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-344">TABLE_OWNER</span></span>|<span data-ttu-id="4c644-345">String</span><span class="sxs-lookup"><span data-stu-id="4c644-345">String</span></span>|
|<span data-ttu-id="4c644-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-346">TABLE_NAME</span></span>|<span data-ttu-id="4c644-347">String</span><span class="sxs-lookup"><span data-stu-id="4c644-347">String</span></span>|
|<span data-ttu-id="4c644-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-348">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-349">String</span><span class="sxs-lookup"><span data-stu-id="4c644-349">String</span></span>|
|<span data-ttu-id="4c644-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-350">DATA_TYPE</span></span>|<span data-ttu-id="4c644-351">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-351">Int16</span></span>|
|<span data-ttu-id="4c644-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-352">TYPE_NAME</span></span>|<span data-ttu-id="4c644-353">String</span><span class="sxs-lookup"><span data-stu-id="4c644-353">String</span></span>|
|<span data-ttu-id="4c644-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4c644-354">PRECISION</span></span>|<span data-ttu-id="4c644-355">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-355">Int32</span></span>|
|<span data-ttu-id="4c644-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-356">LENGTH</span></span>|<span data-ttu-id="4c644-357">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-357">Int32</span></span>|
|<span data-ttu-id="4c644-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="4c644-358">SCALE</span></span>|<span data-ttu-id="4c644-359">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-359">Int16</span></span>|
|<span data-ttu-id="4c644-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-360">RADIX</span></span>|<span data-ttu-id="4c644-361">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-361">Int16</span></span>|
|<span data-ttu-id="4c644-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-362">NULLABLE</span></span>|<span data-ttu-id="4c644-363">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-363">Int16</span></span>|
|<span data-ttu-id="4c644-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-364">REMARKS</span></span>|<span data-ttu-id="4c644-365">String</span><span class="sxs-lookup"><span data-stu-id="4c644-365">String</span></span>|
|<span data-ttu-id="4c644-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-367">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="4c644-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4c644-368">Procedures</span></span>

|<span data-ttu-id="4c644-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-369">ColumnName</span></span>|<span data-ttu-id="4c644-370">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4c644-372">String</span><span class="sxs-lookup"><span data-stu-id="4c644-372">String</span></span>|
|<span data-ttu-id="4c644-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4c644-374">String</span><span class="sxs-lookup"><span data-stu-id="4c644-374">String</span></span>|
|<span data-ttu-id="4c644-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-376">String</span><span class="sxs-lookup"><span data-stu-id="4c644-376">String</span></span>|
|<span data-ttu-id="4c644-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4c644-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="4c644-378">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-378">Int16</span></span>|
|<span data-ttu-id="4c644-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4c644-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="4c644-380">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-380">Int16</span></span>|
|<span data-ttu-id="4c644-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="4c644-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="4c644-382">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-382">Int16</span></span>|
|<span data-ttu-id="4c644-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-383">REMARKS</span></span>|<span data-ttu-id="4c644-384">String</span><span class="sxs-lookup"><span data-stu-id="4c644-384">String</span></span>|
|<span data-ttu-id="4c644-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4c644-386">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="4c644-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4c644-387">ProcedureColumns</span></span>

|<span data-ttu-id="4c644-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-388">ColumnName</span></span>|<span data-ttu-id="4c644-389">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4c644-391">String</span><span class="sxs-lookup"><span data-stu-id="4c644-391">String</span></span>|
|<span data-ttu-id="4c644-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4c644-393">String</span><span class="sxs-lookup"><span data-stu-id="4c644-393">String</span></span>|
|<span data-ttu-id="4c644-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-395">String</span><span class="sxs-lookup"><span data-stu-id="4c644-395">String</span></span>|
|<span data-ttu-id="4c644-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-396">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-397">String</span><span class="sxs-lookup"><span data-stu-id="4c644-397">String</span></span>|
|<span data-ttu-id="4c644-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-398">COLUMN_TYPE</span></span>|<span data-ttu-id="4c644-399">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-399">Int16</span></span>|
|<span data-ttu-id="4c644-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-400">DATA_TYPE</span></span>|<span data-ttu-id="4c644-401">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-401">Int16</span></span>|
|<span data-ttu-id="4c644-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-402">TYPE_NAME</span></span>|<span data-ttu-id="4c644-403">String</span><span class="sxs-lookup"><span data-stu-id="4c644-403">String</span></span>|
|<span data-ttu-id="4c644-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4c644-404">PRECISION</span></span>|<span data-ttu-id="4c644-405">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-405">Int32</span></span>|
|<span data-ttu-id="4c644-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-406">LENGTH</span></span>|<span data-ttu-id="4c644-407">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-407">Int32</span></span>|
|<span data-ttu-id="4c644-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="4c644-408">SCALE</span></span>|<span data-ttu-id="4c644-409">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-409">Int16</span></span>|
|<span data-ttu-id="4c644-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-410">RADIX</span></span>|<span data-ttu-id="4c644-411">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-411">Int16</span></span>|
|<span data-ttu-id="4c644-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-412">NULLABLE</span></span>|<span data-ttu-id="4c644-413">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-413">Int16</span></span>|
|<span data-ttu-id="4c644-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-414">REMARKS</span></span>|<span data-ttu-id="4c644-415">String</span><span class="sxs-lookup"><span data-stu-id="4c644-415">String</span></span>|
|<span data-ttu-id="4c644-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="4c644-416">OVERLOAD</span></span>|<span data-ttu-id="4c644-417">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-417">Int32</span></span>|
|<span data-ttu-id="4c644-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-419">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="4c644-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="4c644-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="4c644-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="4c644-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="4c644-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="4c644-422">Tables</span></span>

- <span data-ttu-id="4c644-423">Índices</span><span class="sxs-lookup"><span data-stu-id="4c644-423">Indexes</span></span>

- <span data-ttu-id="4c644-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="4c644-424">Columns</span></span>

- <span data-ttu-id="4c644-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4c644-425">Procedures</span></span>

- <span data-ttu-id="4c644-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4c644-426">ProcedureColumns</span></span>

- <span data-ttu-id="4c644-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4c644-427">ProcedureParameters</span></span>

- <span data-ttu-id="4c644-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="4c644-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="4c644-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="4c644-429">Tables and Views</span></span>

|<span data-ttu-id="4c644-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-430">ColumnName</span></span>|<span data-ttu-id="4c644-431">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4c644-433">String</span><span class="sxs-lookup"><span data-stu-id="4c644-433">String</span></span>|
|<span data-ttu-id="4c644-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-434">TABLE_OWNER</span></span>|<span data-ttu-id="4c644-435">String</span><span class="sxs-lookup"><span data-stu-id="4c644-435">String</span></span>|
|<span data-ttu-id="4c644-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-436">TABLE_NAME</span></span>|<span data-ttu-id="4c644-437">String</span><span class="sxs-lookup"><span data-stu-id="4c644-437">String</span></span>|
|<span data-ttu-id="4c644-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-438">TABLE_TYPE</span></span>|<span data-ttu-id="4c644-439">String</span><span class="sxs-lookup"><span data-stu-id="4c644-439">String</span></span>|
|<span data-ttu-id="4c644-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-440">REMARKS</span></span>|<span data-ttu-id="4c644-441">String</span><span class="sxs-lookup"><span data-stu-id="4c644-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="4c644-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="4c644-442">Columns</span></span>

|<span data-ttu-id="4c644-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-443">ColumnName</span></span>|<span data-ttu-id="4c644-444">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="4c644-446">String</span><span class="sxs-lookup"><span data-stu-id="4c644-446">String</span></span>|
|<span data-ttu-id="4c644-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-447">TABLE_OWNER</span></span>|<span data-ttu-id="4c644-448">String</span><span class="sxs-lookup"><span data-stu-id="4c644-448">String</span></span>|
|<span data-ttu-id="4c644-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-449">TABLE_NAME</span></span>|<span data-ttu-id="4c644-450">String</span><span class="sxs-lookup"><span data-stu-id="4c644-450">String</span></span>|
|<span data-ttu-id="4c644-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-451">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-452">String</span><span class="sxs-lookup"><span data-stu-id="4c644-452">String</span></span>|
|<span data-ttu-id="4c644-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-453">DATA_TYPE</span></span>|<span data-ttu-id="4c644-454">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-454">Int16</span></span>|
|<span data-ttu-id="4c644-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-455">TYPE_NAME</span></span>|<span data-ttu-id="4c644-456">String</span><span class="sxs-lookup"><span data-stu-id="4c644-456">String</span></span>|
|<span data-ttu-id="4c644-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4c644-457">PRECISION</span></span>|<span data-ttu-id="4c644-458">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-458">Int32</span></span>|
|<span data-ttu-id="4c644-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-459">LENGTH</span></span>|<span data-ttu-id="4c644-460">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-460">Int32</span></span>|
|<span data-ttu-id="4c644-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="4c644-461">SCALE</span></span>|<span data-ttu-id="4c644-462">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-462">Int16</span></span>|
|<span data-ttu-id="4c644-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-463">RADIX</span></span>|<span data-ttu-id="4c644-464">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-464">Int16</span></span>|
|<span data-ttu-id="4c644-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-465">NULLABLE</span></span>|<span data-ttu-id="4c644-466">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-466">Int16</span></span>|
|<span data-ttu-id="4c644-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-467">REMARKS</span></span>|<span data-ttu-id="4c644-468">String</span><span class="sxs-lookup"><span data-stu-id="4c644-468">String</span></span>|
|<span data-ttu-id="4c644-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-470">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="4c644-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4c644-471">Procedures</span></span>

|<span data-ttu-id="4c644-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-472">ColumnName</span></span>|<span data-ttu-id="4c644-473">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4c644-475">String</span><span class="sxs-lookup"><span data-stu-id="4c644-475">String</span></span>|
|<span data-ttu-id="4c644-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4c644-477">String</span><span class="sxs-lookup"><span data-stu-id="4c644-477">String</span></span>|
|<span data-ttu-id="4c644-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-479">String</span><span class="sxs-lookup"><span data-stu-id="4c644-479">String</span></span>|
|<span data-ttu-id="4c644-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4c644-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="4c644-481">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-481">Int16</span></span>|
|<span data-ttu-id="4c644-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="4c644-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="4c644-483">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-483">Int16</span></span>|
|<span data-ttu-id="4c644-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="4c644-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="4c644-485">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-485">Int16</span></span>|
|<span data-ttu-id="4c644-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-486">REMARKS</span></span>|<span data-ttu-id="4c644-487">String</span><span class="sxs-lookup"><span data-stu-id="4c644-487">String</span></span>|
|<span data-ttu-id="4c644-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4c644-489">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="4c644-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4c644-490">ProcedureColumns</span></span>

|<span data-ttu-id="4c644-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-491">ColumnName</span></span>|<span data-ttu-id="4c644-492">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="4c644-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="4c644-494">String</span><span class="sxs-lookup"><span data-stu-id="4c644-494">String</span></span>|
|<span data-ttu-id="4c644-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c644-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="4c644-496">String</span><span class="sxs-lookup"><span data-stu-id="4c644-496">String</span></span>|
|<span data-ttu-id="4c644-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-498">String</span><span class="sxs-lookup"><span data-stu-id="4c644-498">String</span></span>|
|<span data-ttu-id="4c644-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-499">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-500">String</span><span class="sxs-lookup"><span data-stu-id="4c644-500">String</span></span>|
|<span data-ttu-id="4c644-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-501">COLUMN_TYPE</span></span>|<span data-ttu-id="4c644-502">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-502">Int16</span></span>|
|<span data-ttu-id="4c644-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-503">DATA_TYPE</span></span>|<span data-ttu-id="4c644-504">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-504">Int16</span></span>|
|<span data-ttu-id="4c644-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-505">TYPE_NAME</span></span>|<span data-ttu-id="4c644-506">String</span><span class="sxs-lookup"><span data-stu-id="4c644-506">String</span></span>|
|<span data-ttu-id="4c644-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="4c644-507">PRECISION</span></span>|<span data-ttu-id="4c644-508">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-508">Int32</span></span>|
|<span data-ttu-id="4c644-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-509">LENGTH</span></span>|<span data-ttu-id="4c644-510">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-510">Int32</span></span>|
|<span data-ttu-id="4c644-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="4c644-511">SCALE</span></span>|<span data-ttu-id="4c644-512">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-512">Int16</span></span>|
|<span data-ttu-id="4c644-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-513">RADIX</span></span>|<span data-ttu-id="4c644-514">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-514">Int16</span></span>|
|<span data-ttu-id="4c644-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-515">NULLABLE</span></span>|<span data-ttu-id="4c644-516">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-516">Int16</span></span>|
|<span data-ttu-id="4c644-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-517">REMARKS</span></span>|<span data-ttu-id="4c644-518">String</span><span class="sxs-lookup"><span data-stu-id="4c644-518">String</span></span>|
|<span data-ttu-id="4c644-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="4c644-519">OVERLOAD</span></span>|<span data-ttu-id="4c644-520">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-520">Int32</span></span>|
|<span data-ttu-id="4c644-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-522">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="4c644-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4c644-523">ProcedureParameters</span></span>

|<span data-ttu-id="4c644-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="4c644-524">ColumnName</span></span>|<span data-ttu-id="4c644-525">DataType</span><span class="sxs-lookup"><span data-stu-id="4c644-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="4c644-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="4c644-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="4c644-527">String</span><span class="sxs-lookup"><span data-stu-id="4c644-527">String</span></span>|
|<span data-ttu-id="4c644-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="4c644-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="4c644-529">String</span><span class="sxs-lookup"><span data-stu-id="4c644-529">String</span></span>|
|<span data-ttu-id="4c644-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="4c644-531">String</span><span class="sxs-lookup"><span data-stu-id="4c644-531">String</span></span>|
|<span data-ttu-id="4c644-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-532">COLUMN_NAME</span></span>|<span data-ttu-id="4c644-533">String</span><span class="sxs-lookup"><span data-stu-id="4c644-533">String</span></span>|
|<span data-ttu-id="4c644-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-534">COLUMN_TYPE</span></span>|<span data-ttu-id="4c644-535">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-535">Int16</span></span>|
|<span data-ttu-id="4c644-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-536">DATA_TYPE</span></span>|<span data-ttu-id="4c644-537">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-537">Int16</span></span>|
|<span data-ttu-id="4c644-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c644-538">TYPE_NAME</span></span>|<span data-ttu-id="4c644-539">String</span><span class="sxs-lookup"><span data-stu-id="4c644-539">String</span></span>|
|<span data-ttu-id="4c644-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4c644-540">COLUMN_SIZE</span></span>|<span data-ttu-id="4c644-541">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-541">Int32</span></span>|
|<span data-ttu-id="4c644-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="4c644-543">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-543">Int32</span></span>|
|<span data-ttu-id="4c644-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="4c644-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="4c644-545">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-545">Int16</span></span>|
|<span data-ttu-id="4c644-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="4c644-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="4c644-547">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-547">Int16</span></span>|
|<span data-ttu-id="4c644-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-548">NULLABLE</span></span>|<span data-ttu-id="4c644-549">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-549">Int16</span></span>|
|<span data-ttu-id="4c644-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="4c644-550">REMARKS</span></span>|<span data-ttu-id="4c644-551">String</span><span class="sxs-lookup"><span data-stu-id="4c644-551">String</span></span>|
|<span data-ttu-id="4c644-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="4c644-552">COLUMN_DEF</span></span>|<span data-ttu-id="4c644-553">String</span><span class="sxs-lookup"><span data-stu-id="4c644-553">String</span></span>|
|<span data-ttu-id="4c644-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4c644-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="4c644-555">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-555">Int16</span></span>|
|<span data-ttu-id="4c644-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="4c644-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="4c644-557">Int16</span><span class="sxs-lookup"><span data-stu-id="4c644-557">Int16</span></span>|
|<span data-ttu-id="4c644-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4c644-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="4c644-559">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-559">Int32</span></span>|
|<span data-ttu-id="4c644-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4c644-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="4c644-561">Int32</span><span class="sxs-lookup"><span data-stu-id="4c644-561">Int32</span></span>|
|<span data-ttu-id="4c644-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4c644-562">IS_NULLABLE</span></span>|<span data-ttu-id="4c644-563">String</span><span class="sxs-lookup"><span data-stu-id="4c644-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="4c644-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c644-564">See also</span></span>

- [<span data-ttu-id="4c644-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="4c644-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
