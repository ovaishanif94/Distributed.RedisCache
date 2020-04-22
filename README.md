# Distributed.RedisCache
High performance distributed cache helper with the support of serialization and deserialization, incorporating both synchronous and asynchronous using implementation of IDistributedCache.

[![GitHub license](https://img.shields.io/github/license/ovaishanif94/Distributed.RedisCache.svg)](https://github.com/ovaishanif94/Distributed.RedisCache/blob/master/LICENSE) [![Nuget downloads](https://img.shields.io/nuget/dt/Distributed.RedisCache.svg)](https://www.nuget.org/packages/Distributed.RedisCache/) [![Nuget version](https://img.shields.io/nuget/v/Distributed.RedisCache.svg)](https://www.nuget.org/packages/Distributed.RedisCache/) [![GitHub issues](https://img.shields.io/github/issues/ovaishanif94/Distributed.RedisCache.svg)](https://GitHub.com/ovaishanif94/Distributed.RedisCache/issues/) [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/ovaishanif94/Distributed.RedisCache/graphs/commit-activity)

### Download or Install
The latest stable release is available on NuGet: https://www.nuget.org/packages/Distributed.RedisCache

`Install-Package Distributed.RedisCache -Version 3.1.0`

#### Example
**Startup.cs**

    // import package
    using Distributed.RedisCache;
    
    // Configure redis cache
    services.AddRedisCache(x =>
    {
        x.Configuration = "localhost:6379";
        x.InstanceName = "default";
    });
    
**IRedisCache**

    /// <summary>
    /// Get cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <returns>string</returns>
    string Get(string cacheKey);
    
    /// <summary>
    /// Get or set cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="func">This function will trigger only if cache is empty</param>
    /// <param name="options">Expiry of cache</param>
    /// <returns>string</returns>
    string Get(string cacheKey, Func<string> func, Action<DistributedCacheEntryOptions> options);
    
    /// <summary>
    /// Get cache value
    /// </summary>
    /// <typeparam name="T">Type of value</typeparam>
    /// <param name="cacheKey">Caching key</param>
    /// <returns>T</returns>
    T Get<T>(string cacheKey) where T : class;
    
    /// <summary>
    /// Get or set cache value
    /// </summary>
    /// <typeparam name="T">Type of value</typeparam>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="func">This function will trigger only if cache is empty</param>
    /// <param name="options">Expiry of cache</param>
    /// <returns>T</returns>
    T Get<T>(string cacheKey, Func<T> func, Action<DistributedCacheEntryOptions> options) where T : class;
    
    /// <summary>
    /// Get cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <returns>Task<string></returns>
    Task<string> GetAsync(string cacheKey);
    
    /// <summary>
    /// Get or set cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="func">This function will trigger only if cache is empty</param>
    /// <param name="options">Expiry of cache</param>
    /// <returns>Task<string></returns>
    Task<string> GetAsync(string cacheKey, Func<Task<string>> func, Action<DistributedCacheEntryOptions> options);
    
    /// <summary>
    /// Get cache value
    /// </summary>
    /// <typeparam name="T">Type of value</typeparam>
    /// <param name="cacheKey">Caching key</param>
    /// <returns>Task<T></returns>
    Task<T> GetAsync<T>(string cacheKey) where T : class;
    
    /// <summary>
    /// Get or set cache value
    /// </summary>
    /// <typeparam name="T">Type of value</typeparam>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="func">This function will trigger only if cache is empty</param>
    /// <param name="options">Expiry of cache</param>
    /// <returns>Task<T></returns>
    Task<T> GetAsync<T>(string cacheKey, Func<Task<T>> func, Action<DistributedCacheEntryOptions> options) where T : class;
    
    /// <summary>
    /// Refresh cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    void Refresh(string cacheKey);
    
    /// <summary>
    /// Refresh cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <returns>Task</returns>
    Task RefreshAsync(string cacheKey);
    
    /// <summary>
    /// Remove cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    void Remove(string cacheKey);
    
    /// <summary>
    /// Remove cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <returns>Task</returns>
    Task RemoveAsync(string cacheKey);
    
    /// <summary>
    /// Set cache value
    /// </summary>
    /// <typeparam name="T">Type of value</typeparam>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="value">Value to set</param>
    /// <param name="options">Expiry of cache</param>
    void Set<T>(string cacheKey, T value, Action<DistributedCacheEntryOptions> options) where T : class;
    
    /// <summary>
    /// Set cache value
    /// </summary>
    /// <typeparam name="T">Type of value</typeparam>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="value">Value to set</param>
    /// <param name="options">Expiry of cache</param>
    /// <returns>Task</returns>
    Task SetAsync<T>(string cacheKey, T value, Action<DistributedCacheEntryOptions> options) where T : class;
    
    /// <summary>
    /// Set cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="value">Value to set</param>
    /// <param name="options">Expiry of cache</param>
    void SetString(string cacheKey, string value, Action<DistributedCacheEntryOptions> options);
    
    /// <summary>
    /// Set cache value
    /// </summary>
    /// <param name="cacheKey">Caching key</param>
    /// <param name="value">Value to set</param>
    /// <param name="options">Expiry of cache</param>
    /// <returns>Task</returns>
    Task SetStringAsync(string cacheKey, string value, Action<DistributedCacheEntryOptions> options);

# Buy me a coffee :coffee:

ETH: 0xC32Cce6e9A2C88fBe77430B94306C2Db443c06d4

BTC: 1MWVz2MFuHrnTfzxZ8GUSiZXgKuTuRHNLW

BCH: bitcoincash:qr8xav6nzhaj2l9xutvhps36sgxcn8nknge0jz567s
