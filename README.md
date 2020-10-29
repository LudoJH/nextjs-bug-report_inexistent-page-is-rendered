# Bug report

## Describe the bug
With dynamic route, getStaticProps and fallback set to true, when I try to access a non existing slug, it created an HTML & JSON file in .next folder.

For example, if I tries to access /posts/inexistent-slug, nextjs creates 2 files (`inexistent-slug.json` and `inexistent-slug.html` in the folder: `.next/server/pages/posts/`).

It doesn't seems to be a correct behavior, because this can lead to have big amount of files created inside of the .next folder.

## To Reproduce

Repository to reproduce: [https://github.com/LudoJH/nextjs-bug-report_inexistent-page-is-rendered](https://github.com/LudoJH/nextjs-bug-report_inexistent-page-is-rendered) (based on nextjs blog-starter example)

Basically:
1. In `/pages/posts/[slug].js`, I've set fallback to 'true'
2. Run `npm install`,  `npm run build` and `npm run start`
3. Access this link: [http://localhost:3000/posts/inexistent-slug](http://localhost:3000/posts/inexistent-slug)
4. The two files (inexistent-slug.html and inexistent-slug.json) have been created in .next/server/page/posts

## Expected behavior
When trying to access a page with a slug that does not exist, it would be expected that no HTML or JSON file are created for this slug.

## Screenshots

## System information

- OS: macOS
- Browser (if applies): chrome
- Version of Next.js: 10.0.0
- Version of Node.js: 12.19.0
