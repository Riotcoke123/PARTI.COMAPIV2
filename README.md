<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <!-- Tailwind CSS CDN -->
</head>

<body class="bg-gray-100 min-h-screen py-10 px-4 sm:px-6 lg:px-8">
  <div class="max-w-4xl mx-auto bg-white border border-gray-300 rounded-lg shadow-sm overflow-hidden">
    <div class="bg-gray-50 px-5 py-3 border-b border-gray-200 flex items-center gap-3">
      <img
        src="https://github.com/user-attachments/assets/8aefdbc2-8e48-43e9-a549-6df85a4424ac"
        alt="PARTI.COM"
        width="60"
        height="60"
        class="rounded"
      />
      <h1 class="text-xl font-semibold text-gray-800">Parti API v2 Documentation</h1>
    </div>
    <div class="p-6 md:p-8">
      <h1 class="text-3xl font-bold text-gray-900 border-b border-gray-200 pb-3 mb-6">Parti API v2</h1>
      <p class="text-gray-700 leading-relaxed mb-6">
        Welcome to the unofficial documentation for the Parti API v2. This API provides access to user profiles,
        livestream information, and related content.
      </p>
      <!-- Getting Started -->
      <h2 class="text-2xl font-semibold text-gray-900 border-b border-gray-200 pb-2 mt-8 mb-4">
        Getting Started & Authentication
      </h2>
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">Finding the Streamer User ID</h3>
      <p class="text-gray-600 mb-3">
        Most API endpoints require a <code>{user_id}</code> parameter. For a streamer on parti.com, this ID can often be found by:
      </p>
      <ol class="list-decimal list-inside text-gray-700 ml-4 mb-6 space-y-2">
        <li>Opening your browser's Developer Tools (F12 or Cmd+Option+I).</li>
        <li>Navigating to the <strong>Network</strong> tab.</li>
        <li>Filtering network requests for keywords like <code>parti_v2</code> or <code>user_profile</code> while viewing the streamer's page.</li>
        <li>The <code>user_id</code> is typically a long numeric string found within the request or response payloads.</li>
      </ol>
      <!-- Base URL -->
      <h2 class="text-2xl font-semibold text-gray-900 border-b border-gray-200 pb-2 mt-8 mb-4">Base URL</h2>
      <p class="text-gray-700 mb-2">All API endpoints are relative to the following base URL:</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">https://backend-prod-1053646558307.us-central1.run.app/parti_v2</code>
      </pre>
      <!-- API Endpoints -->
      <h2 class="text-2xl font-semibold text-gray-900 border-b border-gray-200 pb-2 mt-8 mb-4">API Endpoints</h2>
      <p class="text-gray-700 mb-6">
        The following endpoints are available. All endpoints use the
        <code class="bg-gray-200 rounded px-1.5 py-0.5 font-mono text-sm">GET</code> method unless otherwise specified.
      </p>
      <!-- 1. Get User Profile -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">1. Get User Profile</h3>
      <p class="text-gray-600 mb-3">Fetches public profile information for a specific user.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/user_profile/{user_id}</code></pre>
      <h4 class="font-semibold text-gray-700 mt-3 mb-1">URL Parameters:</h4>
      <ul class="list-disc list-inside text-gray-700 mb-6">
        <li><code class="bg-gray-200 rounded px-1.5 py-0.5 font-mono text-sm">{user_id}</code> — The unique identifier for the user.</li>
      </ul>
      <!-- 2. Get Livestream Channel Info -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">2. Get Livestream Channel Info</h3>
      <p class="text-gray-600 mb-3">Retrieves information about a user's livestream channel.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/get_livestream_channel_info/{user_id}</code></pre>
      <ul class="list-disc list-inside text-gray-700 mb-6">
        <li><code class="bg-gray-200 rounded px-1.5 py-0.5 font-mono text-sm">{user_id}</code> — The unique identifier for the streamer.</li>
      </ul>
      <!-- 3. Get User Profile Feed -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">3. Get User Profile Feed</h3>
      <p class="text-gray-600 mb-3">Gets a paginated feed of content from a user's profile.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/user_profile_feed/{user_id}</code></pre>
      <ul class="list-disc list-inside text-gray-700 mb-3">
        <li><code class="bg-gray-200 rounded px-1.5 py-0.5 font-mono text-sm">{user_id}</code> — User ID.</li>
      </ul>
      <h4 class="font-semibold text-gray-700 mt-3 mb-1">Query Parameters:</h4>
      <ul class="list-disc list-inside text-gray-700 mb-6">
        <li><code class="bg-gray-200 rounded px-1.5 py-0.5 font-mono text-sm">limit</code> — Number of items to return (e.g., 5).</li>
      </ul>
      <!-- 4. Get Livestream Moderators -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">4. Get Livestream Moderators</h3>
      <p class="text-gray-600 mb-3">Lists the moderators for a user's livestream.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/livestream/moderators/{user_id}</code></pre>
      <!-- 5. Get Livestream Banner -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">5. Get Livestream Banner</h3>
      <p class="text-gray-600 mb-3">Retrieves the banner image for a user's livestream.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/livestream/banner/{user_id}</code></pre>
      <!-- 6. Get User Currency Info -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">6. Get User Currency Info</h3>
      <p class="text-gray-600 mb-3">Fetches information about a user's currency.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/user_currency_info/{user_id}</code></pre>
      <!-- 7. Get Pinned Message -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">7. Get Pinned Message</h3>
      <p class="text-gray-600 mb-3">Retrieves the pinned message for a user's profile or channel.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/pinned_message/{user_id}</code></pre>
      <!-- 8. Get Creator Details -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">8. Get Creator Details (Stripe Integration)</h3>
      <p class="text-gray-600 mb-3">Retrieves integration details for a creator, likely related to payment processing (Stripe).</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/stripe/get_creator_details/{user_id}</code></pre>
      <!-- 9. Get Assets Prices Info -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">9. Get Assets Prices Info</h3>
      <p class="text-gray-600 mb-3">Retrieves information on the prices of various platform assets or virtual goods.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/assets_prices/info</code></pre>
      <!-- 10. Get Featured Channels -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">10. Get Featured Channels</h3>
      <p class="text-gray-600 mb-3">Lists the channels currently being promoted or featured on the platform.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/featured_channels</code></pre>
      <!-- 11. Get Live Channel Info -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">11. Get Live Channel Info (Paginated)</h3>
      <p class="text-gray-600 mb-3">Fetches a paginated list of currently live streaming channels.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/get_livestream_channel_info/live</code></pre>
      <ul class="list-disc list-inside text-gray-700 mb-6">
        <li><code class="bg-gray-200 px-1.5 py-0.5 rounded font-mono text-sm">limit</code> — Maximum number of channels to return (e.g., 30 or 100).</li>
        <li><code class="bg-gray-200 px-1.5 py-0.5 rounded font-mono text-sm">offset</code> — Starting index for the list (e.g., 0).</li>
      </ul>
      <!-- 12. Livestream Calendar Events -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">12. Get Livestream Calendar Events</h3>
      <p class="text-gray-600 mb-3">Retrieves a paginated list of upcoming scheduled livestream events.</p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/livestream_calendar/events</code></pre>
      <!-- 13. Recent Livestreams -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">13. Get Recent Livestream Channel Info (Paginated/Filtered)</h3>
      <p class="text-gray-600 mb-3">
        Fetches a paginated list of recent livestream channels, with options for sorting and filtering by a specific user ID.
      </p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/get_livestream_channel_info/recent</code></pre>
      <h4 class="font-semibold text-gray-700 mt-3 mb-1">Query Parameters:</h4>
      <ul class="list-disc list-inside text-gray-700 mb-3">
        <li><code class="bg-gray-200 px-1.5 py-0.5 rounded font-mono text-sm">sort_by_date_desc</code> — Whether to sort results by date descending.</li>
        <li><code class="bg-gray-200 px-1.5 py-0.5 rounded font-mono text-sm">by_user_id</code> — Filter results to include only channels from this user.</li>
        <li><code class="bg-gray-200 px-1.5 py-0.5 rounded font-mono text-sm">limit</code> — Number of channels to return (e.g., 10).</li>
        <li><code class="bg-gray-200 px-1.5 py-0.5 rounded font-mono text-sm">offset</code> — Starting index for pagination.</li>
      </ul>
      <h4 class="font-semibold text-gray-700 mt-3 mb-1">Example Request:</h4>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">
https://backend-prod-1053646558307.us-central1.run.app/parti_v2/profile/get_livestream_channel_info/recent?sort_by_date_desc=true&by_user_id=123456&offset=0&limit=10
</code></pre>
      <!-- 14. Get Specific Livestream Event -->
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">14. Get Specific Recent Livestream Channel Info by Event ID</h3>
      <p class="text-gray-600 mb-3">
        Retrieves detailed information for a specific recent livestream using its unique event identifier.
      </p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">/profile/get_livestream_channel_info/recent/{event_id}</code></pre>
      <ul class="list-disc list-inside text-gray-700 mb-6">
        <li><code class="bg-gray-200 rounded px-1.5 py-0.5 font-mono text-sm">{event_id}</code> — Unique identifier for the livestream event.</li>
      </ul>
      <!-- Example Asset URLs -->
      <h2 class="text-2xl font-semibold text-gray-900 border-b border-gray-200 pb-2 mt-8 mb-4">Example Asset URLs</h2>
      <p class="text-gray-700 mb-6">
        This section contains examples of URLs for assets or streams that may be referenced by the API.
      </p>
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">1. Segmented HLS Stream URL Template</h3>
      <p class="text-gray-600 mb-3">
        Template for retrieving a specific segment or resolution of the HLS stream, useful for VOD or multi-resolution streaming.
      </p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">
https://storage.firstlookforyou.com/channels/dev-channel-{user_id}/live/current/20251027T225041Z/hls_1080p60/index-1.m3u8
</code></pre>
      <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">2. Main HLS Stream Playlist URL Template</h3>
      <p class="text-gray-600 mb-3">
        Template for the main HLS playlist (.m3u8) file, typically containing links to resolution variants.
      </p>
      <pre class="bg-gray-100 p-4 rounded-md overflow-x-auto">
<code class="font-mono text-sm text-gray-800">
https://storage.firstlookforyou.com/channels/dev-channel-{user_id}/live/current/main.m3u8
</code></pre>
    </div>
  </div>
</body>
</html>

