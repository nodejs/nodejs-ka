#### io.js-ის ყოველკვირეული მიმოხილვა. 6 თებერვალი, 2015 წელი

:fire: Atom-ი და nw.js-ი უკვე io.js-ზე, Linux Tracing-ი და კიდევ ბევრი სხვა.

ყოველ პარასკევს, ჩვენ გამოვაქვეყნებთ ყოველკვიურეულ სიახლეებს თუ რა ხდება io.js-ში და მის გარშემო.

ჩვენ გადავხედეთ კონტრიბუციების რაოდენობას იანვარში და აღმოვაჩინეთ, რომ **მე-3 ყველაზე აქტიური კვირა იყო Node-ის ისტორიაში(294 კომიტი)** და თითქმის ყველაზე აქტიური თვე მთელი **სამი წლის განმავლობაში(308 კომიტი 2012 წლის იანვარში)**. კონტრიბუციის ზრდის მიხედვით ველოდებით, რომ თებერვალი უფრო აქტიური იქნება.

1. გამოვიდა [1.1.0][1] ვერსია, იხილეთ **[ცვლილებების ისტორია][2]**
2. დაემატა **[გამარტივებული Stream-ების კონსტრუქცია][3]** Sam Newman-სგან
3. დაემატა **ლინუქს თრეისინგი** (LTTNG)
4. Google [ავრცელებს **tracing-ზე თავიანთ საქმიანობას**][5] **v8-ში და Chrome-ში** როცა ამავდროულად ჩვენ ვაწარმოებთ კოლაბორაციას io.js-ის debugging-ის გარშემო
5. [დაემატა io.js-ის მხარდაჭერა **Travis CI**-ში][6].
6. [დაემატა io.js-ის მხარდაჭერა **Codeship**-ში][7].
7. [**Atom ედიტორი** გადავიდა io.js-ზე][8].
8. **nw.js** (ძველად **node-webkit**) [გადავიდა io.js-ზე][9].
9. ახალი **Tessel**-ის Hardware-ში [იქნება io.js-ის მხარდაჭერა][10].
10. Chris Dickinson-მა დაამატა [**6 ახალი კომიტერი**][11], რის შემდეგაც სრული აქტიური **კომიტერების რაოდენობა გახდა 23**
11. მუშაობა დაიწყო [**სტაბილურობის და თავსებადობის შესახებ**][12]. სასურველია საზოგადოების მონაწილეობის მიღება ამ საქმეში
12. დავიწყეთ [კომპანიებთან კონტაქტი და მათი აზრის მოსმენა][13] ჩვენს **გეგმასთან** დაკავშირებით. თუ გაქვთ იმ კომპანიების საკონტაქტო ინფორმაცია რომლებიც გამოგვრჩა, გთხოვთ შეგვატყობინოთ.
13. შემდეგ კვირას არის [**Node Summit**][14] სადაც ბევრი io.js-ის წარმომადგენელი ესწრება და საუბრობს
14. [ყოველკვირეული TC მიტინგი][15]
15. [ვებგვერდის მომუშავე ჯგუფის შეხვედრა][16]
16. [Tracing-ის მომუშავე ჯგუფის შეხვედრა][17]

[1]: https://iojs.org/dist/v1.1.0/
[2]: https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md#2015-02-03-version-110-chrisdickinson
[3]: https://github.com/iojs/io.js/commit/50daee7243a3f987e1a28d93c43f913471d6885a
[4]: https://github.com/iojs/io.js/pull/702
[5]: https://github.com/iojs/io.js/issues/671#issuecomment-73191538
[6]: http://docs.travis-ci.com/user/build-environment-updates/2015-02-03/
[7]: https://codeship.com/documentation/languages/nodejs/#iojs
[8]: https://github.com/atom/atom/releases/tag/v0.177.0
[9]: https://github.com/nwjs/nw.js/issues/2742
[10]: http://blog.technical.io/post/110115579867/upcoming-hardware-from-technical-machine
[11]: https://github.com/iojs/io.js/issues/680#issuecomment-73089691
[12]: https://github.com/iojs/io.js/issues/725
[13]: https://github.com/iojs/roadmap/issues/13
[14]: http://nodesummit.com/
[15]: https://www.youtube.com/watch?v=IhXa2FmtBI4
[16]: https://www.youtube.com/watch?v=SBJaXUA0lSY
[17]: https://www.youtube.com/watch?v=Oar2yB5SPtA
