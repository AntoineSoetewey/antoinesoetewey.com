---
description: This is a demo of the Congo theme for Hugo.
title: 'Welcome to Congo! :tada:'
---

{{< lead >}}
A simple, lightweight theme for Hugo built with Tailwind CSS.
{{< /lead >}}

<div class="flex px-4 py-2 mb-8 text-base rounded-md bg-primary-100 dark:bg-primary-900">
  <span class="flex items-center pr-3 text-primary-400">
    {{< icon "exclamation-triangle" >}}
  </span>
  <span class="flex items-center justify-between flex-grow dark:text-neutral-300">
    <span class="prose dark:text-neutral">This is a demo of the <code id="layout">page</code> layout.</span>
    <button
      class="px-4 !text-neutral !no-underline rounded-md bg-primary-600 hover:!bg-primary-500 dark:bg-primary-800 dark:hover:!bg-primary-700"
      onclick="switchLayout()"
    >
      Switch layout &orarr;
    </button>
  </span>
</div>
