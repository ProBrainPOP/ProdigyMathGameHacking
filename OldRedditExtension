const olddit = (tabId, changeInfo, tab) => {
  if (tab.url.match('//old.reddit.com')) return;
  if (tab.url.match('reddit.com')) {
    const { pathname } = new URL(tab.url);
    const oldUrl = `https://old.reddit.com${pathname}`;

    chrome.tabs.executeScript(tabId, {
      code: `window.location.href="${oldUrl}"`,
      runAt: 'document_start'
    });
  }
};

chrome.tabs.onUpdated.addListener(olddit);
