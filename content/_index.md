+++
date = '2025-01-03T21:04:15+08:00'
draft = false
title = 'home of NimPyLib'
description = 'Libraries to write Python in Nim'
keywords = ['Nim', 'Python', 'Library',  'nim-lang', 'pylib', 'meta-programming']
+++


***Write Python in [Nim][]!***

[Nim]: {{<url/nim>}}
[Python]: https://python.org

Python-like operators/functions and libraries as well as syntax sugars

in 
[<img alt=Nim src=img/nim_logo.svg height="7%" width="16%"></img>][Nim]

<details id="repo-list">
  <summary>Children Repos</summary>
  <ul id="repos"></ul>
</details>
<script>
const exclude_repos = ['.github',
  'template',
  'nimpylib', 'website'  // website is this website itself, nimpylib is the main repo
];
const owner = 'nimpylib';
fetch(`https://api.github.com/users/${owner}/repos`)
  .then(r => r.json())
  .then(data => {
    const ul = document.getElementById('repos');
    ul.style.display = 'grid';
    ul.style.gridTemplateColumns = 'max-content';
    // if wanting two rows 'max-content max-content';
    ul.style.columnGap = '12px';
    ul.style.rowGap = '8px';
    ul.style.justifyContent = 'center';
    const badgeOf = (repoName, ciName) => {
      const ymlUrl = `https://github.com/${owner}/${repoName}/actions/workflows/${ciName}.yml`
      const badgeUrl = `${ymlUrl}/badge.svg`
      const img = document.createElement('img')
      img.alt = "";
      img.src = badgeUrl;
      const result = document.createElement('a');
      result.appendChild(img);
      result.href = ymlUrl;
      return result;
    }
    data.forEach(repo => {
      if (exclude_repos.includes(repo.name)) return;
      const li = document.createElement('li');
      li.style.display = 'flex';
      li.style.justifyContent = 'space-between';
      li.style.alignItems = 'center';
      //
      const lhs = document.createElement('div');
      lhs.style.display = 'flex';
      //
      const rhs = document.createElement('div');
      rhs.style.display = 'flex';
      rhs.style.alignItems = 'flex-end';
      rhs.appendChild(badgeOf(repo.name, 'ci'));
      rhs.appendChild(badgeOf(repo.name, 'docs'));
      // 
      const web = document.createElement('a');
      web.href = repo.homepage || repo.html_url;
      web.textContent = repo.name; // 'website';
      web.style.textDecoration = 'none';
      web.style.color = '#0366d6';
      //
      const gh_a = document.createElement('a');
      gh_a.href = repo.html_url;
      gh_a.innerHTML = `<svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" style="vertical-align:middle;fill:currentColor"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"></path></svg><span style="vertical-align:middle;margin-left:6px">github</span>`;
      gh_a.style.display = 'inline-flex';
      gh_a.style.alignItems = 'center';
      gh_a.style.padding = '4px 8px';
      gh_a.style.border = '1px solid #e1e4e8';
      gh_a.style.background = '#f6f8fa';
      gh_a.style.borderRadius = '6px';
      gh_a.style.textDecoration = 'none';
      gh_a.style.color = '#24292f';
      gh_a.style.fontSize = '0.95em';
      //
      lhs.appendChild(gh_a);
      lhs.appendChild(web);
      li.appendChild(lhs);
      li.appendChild(rhs);
      ul.appendChild(li);
    });
  });
</script>

