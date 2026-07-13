/****************************************************************************************
 * NitroFox                                                                          *
 * "SHIMORA"                                                                     
 * priority: Fast Browsing                                                         *
 * version: 152                                                                         *
 * License: MIT                          *
 ***************************************************************************************/

/****************************************************************************
 * SECTION: GENERAL                                                        *
****************************************************************************/
   user_pref("content.switch.threshold", 300000); // HIDDEN; default= 750000; alt=500000
   user_pref("nglayout.initialpaint.delay", 5); // DEFAULT; formerly 250
   user_pref("nglayout.initialpaint.delay_in_oopif", 5); // DEFAULT
   user_pref("gfx.content.skia-font-cache-size", 20); // 20 MB; default=5; Chrome=20
   user_pref("content.notify.ontimer", true); // DEFAULT
   user_pref("content.notify.interval", 100000); // (.10s); default=120000 (.12s)
   user_pref("content.max.tokenizing.time", 1000000); // (1.00s); alt=2000000; HIDDEN
   user_pref("content.interrupt.parsing", true); // HIDDEN
   user_pref("content.switch.threshold", 30000); // HIDDEN; default= 750000; alt=50000
   user_pref("browser.newtab.preload", true); // DEFAULT
   user_pref("dom.ipc.processPriorityManager.backgroundUsesEcoQoS", false)
   user_pref("browser.sessionstore.restore_on_demand", true); // DEFAULT
   user_pref("browser.sessionstore.restore_pinned_tabs_on_demand", true);
   user_pref("browser.sessionstore.restore_tabs_lazily", true); // DEFAULT
/****************************************************************************
 * SECTION: GFX RENDERING TWEAKS                                            *
****************************************************************************/

//user_pref("gfx.webrender.all", true); // enables WR + additional features
//user_pref("gfx.webrender.precache-shaders", true); // longer initial startup time
//user_pref("gfx.webrender.compositor", true); // DEFAULT WINDOWS macOS
    //user_pref("gfx.webrender.compositor.force-enabled", true); // enforce
//user_pref("gfx.webrender.layer-compositor", true);
// PREF: improve CPU usage on AMD systems
    user_pref("media.wmf.zero-copy-nv12-textures-force-enabled", true);
    user_pref("gfx.webrender.software", true); // Software Webrender uses CPU instead of GPU
    user_pref("gfx.webrender.software.opengl", true); // LINUX
    user_pref("gfx.canvas.accelerated", true); // [DEFAULT FF133+]
    user_pref("gfx.canvas.accelerated.cache-items", 8192); // [DEFAULT FF135+]
    user_pref("gfx.canvas.accelerated.cache-size", 512); // default=256; Chrome=512; max=2048
    user_pref("gfx.canvas.max-size", 32767); // [DEFAULT]
	
/****************************************************************************
 * SECTION: DISK CACHE                                                     *
****************************************************************************/

// PREF: force a fixed max cache size on disk
// NOTE: You need this set to false if you are to edit the disk capacity value
   user_pref("browser.cache.disk.smart_size.enabled", false);

// PREF: disk cache size
   user_pref("browser.cache.disk.capacity", 1024000); // default=256000; size of disk cache; 1024000=1GB, 2048000=2GB
   user_pref("browser.cache.disk.max_entry_size", 51200); // DEFAULT (50 MB); maximum size of an object in disk cache

// PREF: cache memory pool
   user_pref("browser.cache.disk.metadata_memory_limit", 1024); // DEFAULT (1 MB); limit of recent metadata we keep in memory for faster access
   user_pref("browser.cache.disk.preload_chunk_count", 8); // default=4
   user_pref("browser.cache.frecency_half_life_hours", 6); // DEFAULT
   user_pref("browser.cache.disk.max_chunks_memory_usage", 40960); // DEFAULT (40 MB)
   user_pref("browser.cache.disk.max_priority_chunks_memory_usage", 40960); // DEFAULT (40 MB)

// PREF: how often to validate document in cache
// 0 = once-per-session
// 1 = each-time
// 2 = never
// 3 = when-appropriate/automatically (default)
    user_pref("browser.cache.check_doc_frequency", 3); // DEFAULT

// PREF: enforce free space checks
// When smartsizing is disabled, we could potentially fill all disk space by
// cache data when the disk capacity is not set correctly. To avoid that, we
// check the free space every time we write some data to the cache. The free
// space is checked against two limits. Once the soft limit is reached we start
// evicting the least useful entries, when we reach the hard limit writing to
// the entry fails.
    user_pref("browser.cache.disk.free_space_soft_limit", 10240); // default=5120 (5 MB)
    user_pref("browser.cache.disk.free_space_hard_limit", 2048); // default=1024 (1 MB)

// PREF: compression level for cached JavaScript bytecode [FF102+]
// [1] https://github.com/yokoffing/Betterfox/issues/247
// 0 = do not compress (default)
// 1 = minimal compression
// 9 = maximal compression
    user_pref("browser.cache.jsbc_compression_level", 3);

/****************************************************************************
 * SECTION: MEMORY CACHE                                                   *
****************************************************************************/

// PREF: memory cache
// The "automatic" size selection (default) is based on a decade-old table
// that only contains settings for systems at or below 8GB of system memory [1].
// Waterfox G6 allows it to go above 8GB machines [3].
// Value can be up to the max size of an unsigned 64-bit integer.
// -1 = Automatically decide the maximum memory to use to cache decoded images,
// messages, and chrome based on the total amount of RAM
// For machines with 8GB+ RAM, that equals 32768 kb = 32 MB
    user_pref("browser.cache.memory.capacity", 65536); // default=32768 (32 MB)
    user_pref("browser.cache.memory.max_entry_size", 10240); // default=5120 (5 MB)

// PREF: amount of Back/Forward cached pages stored in memory for each tab
// Pages that were recently visited are stored in memory in such a way
// that they don't have to be re-parsed. This improves performance
// when pressing Back and Forward. This pref limits the maximum
// number of pages stored in memory. If you are not using the Back
// and Forward buttons that much, but rather using tabs, then there
// is no reason for Firefox to keep memory for this.
// -1=determine automatically (8 pages)

    user_pref("browser.sessionhistory.max_total_viewers", 8); // DEFAULT
    user_pref("browser.sessionstore.max_tabs_undo", 10); // default=25
    user_pref("browser.sessionstore.max_entries", 10); // [HIDDEN OR REMOVED]
    user_pref("dom.storage.default_quota", 20480); // 20MB; default=5120
    user_pref("dom.storage.shadow_writes", true);

// PREF: tell garbage collector to start running when javascript is using xx MB of memory
// Garbage collection releases memory back to the system.
    user_pref("javascript.options.mem.high_water_mark", 128); // DEFAULT [HIDDEN OR REMOVED]

/****************************************************************************
 * SECTION: MEDIA CACHE                                                     *
****************************************************************************/

// PREF: media disk cache
    user_pref("media.cache_size", 512000); // DEFAULT
    user_pref("media.memory_caches_combined_limit_kb", 1048576); // 1GB; default=524288
    user_pref("media.memory_caches_combined_limit_pc_sysmem", 5); // DEFAULT; alt=10; the percentage of system memory that Firefox can use for media caches
    user_pref("media.mediasource.enabled", true); // DEFAULT
    user_pref("media.cache_readahead_limit", 3600); // 10 min; default=60; stop reading ahead when our buffered data is this many seconds ahead of the current playback
    user_pref("media.cache_resume_threshold", 1800); // 5 min; default=30; when a network connection is suspended, don't resume it until the amount of buffered data falls below this threshold

/****************************************************************************
 * SECTION: IMAGE CACHE                                                     *
****************************************************************************/

// PREF: image cache
    user_pref("image.cache.size", 20971520); // (cache images up to 20 MiB in size) [DEFAULT]
    user_pref("image.mem.decode_bytes_at_a_time", 32768); // default=16384; chunk size for calls to the image decoders
    user_pref("image.mem.max_decoded_image_kb", 512000); // 500MB [HIDDEN OR REMOVED?]
    user_pref("image.mem.shared.unmap.min_expiration_ms", 120000); // default=60000; minimum timeout to unmap shared surfaces since they have been last used

/****************************************************************************
 * SECTION: TAB UNLOAD                                                      *
****************************************************************************/

// PREF: unload tabs on low memory
// [ABOUT] about:unloads
// Firefox will detect if your computer’s memory is running low (less than 200MB)
// and suspend tabs that you have not used in awhile.
// [1] https://support.mozilla.org/en-US/kb/unload-inactive-tabs-save-system-memory-firefox
// [2] https://hacks.mozilla.org/2021/10/tab-unloading-in-firefox-93/
user_pref("browser.tabs.unloadOnLowMemory", true); // DEFAULT

// PREF: determine when tabs unload [WINDOWS] [LINUX]
// Notify TabUnloader or send the memory pressure if the memory resource
// notification is signaled AND the available commit space is lower than
// this value (in MiB).
// Set this to some value, e.g. 4/5 of total memory available on your system:
// 4GB=3276, 8GB=6553, 16GB=13107, 32GB=25698, 64GB=52429
user_pref("browser.low_commit_space_threshold_mb", 3276); // default=200; WINDOWS LINUX

// PREF: determine when tabs unload [LINUX]
// On Linux, Firefox checks available memory in comparison to total memory,
// and use this percent value (out of 100) to determine if Firefox is in a
// low memory scenario.
//user_pref("browser.low_commit_space_threshold_percent", 5); // default=5; LINUX

// PREF: determine how long (in ms) tabs are inactive before they unload
// 60000=1min; 300000=5min; 600000=10min (default)
    user_pref("browser.tabs.min_inactive_duration_before_unload", 300000); // 5min; default=600000
