You are a naming assistant. Given a list of file paths and minimal context from a static website, suggest a new filename (basename only, same extension) for each file. Rules:
- Lowercase, kebab-case, no spaces. SEO-friendly and human-readable.
- For HTML: use page purpose (e.g. about-us.html, contact.html). Keep index.html as index.html.
- For CSS/JS: use purpose (e.g. main-styles.css, analytics.js).
- For images: use content (e.g. logo-infygate.webp, hero-banner.webp). Use alt/title when provided.
- Return a JSON object: keys = exact original path strings, values = new basename only (e.g. "main.css"). Preserve extension.
- Do not change path prefix (e.g. css/ stays css/ by returning "name.css" not "css/name.css").

Files and context:
[
  {
    "path": "404.html",
    "context": {
      "title": "",
      "first_heading": "404"
    }
  },
  {
    "path": "about-us.html",
    "context": {
      "title": "Crossroad South Church | About Us",
      "first_heading": "ABOUTUS"
    }
  },
  {
    "path": "blog-a-birth-that-threatened-a-king.html",
    "context": {
      "title": "A BIRTH THAT THREATENED A KING",
      "first_heading": "A BIRTH THAT THREATENED A KING"
    }
  },
  {
    "path": "blog-a-faith-that-suffers-yet-a-faith-that-grows.html",
    "context": {
      "title": "A Faith That Suffers- Yet A Faith That Grows",
      "first_heading": "A Faith That Suffers- Yet A Faith That Grows"
    }
  },
  {
    "path": "blog-a-gospel-outlook-at-the-2-t-s-trials-and-temptations-part-1.html",
    "context": {
      "title": "A GOSPEL OUTLOOK AT THE 2 T\u2019s: TRIALS AND TEMPTATIONS (PART-1)",
      "first_heading": "A GOSPEL OUTLOOK AT THE 2 T\u2019s: TRIALS AND TEMPTATIONS (PART-1)"
    }
  },
  {
    "path": "blog-a-gospel-outlook-at-the-2-t-s-trials-and-temptations-part-2.html",
    "context": {
      "title": "A GOSPEL OUTLOOK AT THE 2 T\u2019s: TRIALS AND TEMPTATIONS (PART-2)",
      "first_heading": "A GOSPEL OUTLOOK AT THE 2 T\u2019s: TRIALS AND TEMPTATIONS (PART-2)"
    }
  },
  {
    "path": "blog-a-gospel-refined-tongue-purged-for-pure-speech.html",
    "context": {
      "title": "A GOSPEL REFINED TONGUE: PURGED FOR PURE SPEECH",
      "first_heading": "A GOSPEL REFINED TONGUE: PURGED FOR PURE SPEECH"
    }
  },
  {
    "path": "blog-a-praying-praising-and-confessional-life-of-a-christian.html",
    "context": {
      "title": "A PRAYING, PRAISING AND CONFESSIONAL LIFE OF A CHRISTIAN",
      "first_heading": "A PRAYING, PRAISING AND CONFESSIONAL LIFE OF A CHRISTIAN"
    }
  },
  {
    "path": "blog-a-trumpet-with-gospel-soul.html",
    "context": {
      "title": "A TRUMPET WITH GOSPEL SOUL",
      "first_heading": "A TRUMPET WITH GOSPEL SOUL"
    }
  },
  {
    "path": "blog-anger-gospel-managed.html",
    "context": {
      "title": "Anger: Gospel Managed",
      "first_heading": "Anger: Gospel Managed"
    }
  },
  {
    "path": "blog-christ-prominent-or-preeminent.html",
    "context": {
      "title": "Christ: Prominent? Or Preeminent?",
      "first_heading": "Christ: Prominent? Or Preeminent?"
    }
  },
  {
    "path": "blog-christ-s-return-a-stimulus-for-holiness-and-endurance.html",
    "context": {
      "title": "CHRIST\u2019S RETURN- A STIMULUS FOR HOLINESS AND ENDURANCE",
      "first_heading": "CHRIST\u2019S RETURN- A STIMULUS FOR HOLINESS AND ENDURANCE"
    }
  },
  {
    "path": "blog-christian-living-a-living-christian.html",
    "context": {
      "title": "Christian Living, A Living Christian",
      "first_heading": "Christian Living, A Living Christian"
    }
  },
  {
    "path": "blog-christian-sanctification-to-walk-to-be-led-to-keep-in-step.html",
    "context": {
      "title": "Christian Sanctification: To Walk-To Be Led-To Keep In Step",
      "first_heading": "Christian Sanctification: To Walk-To Be Led-To Keep In Step"
    }
  },
  {
    "path": "blog-decoding-the-storm-in-galilee.html",
    "context": {
      "title": "Decoding the Storm In Galilee",
      "first_heading": "Decoding the Storm In Galilee"
    }
  },
  {
    "path": "blog-dominion-s-change-when-rulers-change.html",
    "context": {
      "title": "DOMINION\u2019S CHANGE WHEN RULERS CHANGE",
      "first_heading": "DOMINION\u2019S CHANGE WHEN RULERS CHANGE"
    }
  },
  {
    "path": "blog-everyone-is-precious-in-the-sight-of-god.html",
    "context": {
      "title": "Everyone Is Precious In the Sight Of God",
      "first_heading": "Everyone Is Precious In the Sight Of God"
    }
  },
  {
    "path": "blog-faith-that-cleaved-to-the-least-option.html",
    "context": {
      "title": "Faith That Cleaved To The Least Option",
      "first_heading": "Faith That Cleaved To The Least Option"
    }
  },
  {
    "path": "blog-faith-that-evidences-redemptive-favour.html",
    "context": {
      "title": "FAITH THAT EVIDENCES REDEMPTIVE FAVOUR",
      "first_heading": "FAITH THAT EVIDENCES REDEMPTIVE FAVOUR"
    }
  },
  {
    "path": "blog-faith-that-experiences-redemptive-favour.html",
    "context": {
      "title": "FAITH THAT EXPERIENCES REDEMPTIVE FAVOUR",
      "first_heading": "FAITH THAT EXPERIENCES REDEMPTIVE FAVOUR"
    }
  },
  {
    "path": "blog-faithful-christian-living.html",
    "context": {
      "title": "Faithful Christian Living",
      "first_heading": "Faithful Christian Living"
    }
  },
  {
    "path": "blog-faithfulness-born-and-borne-of-the-holy-spirit.html",
    "context": {
      "title": "FAITHFULNESS BORN AND BORNE OF THE HOLY SPIRIT",
      "first_heading": "FAITHFULNESS BORN AND BORNE OF THE HOLY SPIRIT"
    }
  },
  {
    "path": "blog-falling-in-love-again-with-jesus.html",
    "context": {
      "title": "FALLING IN LOVE AGAIN WITH JESUS",
      "first_heading": "FALLING IN LOVE AGAIN WITH JESUS"
    }
  },
  {
    "path": "blog-goodness-born-and-borne-of-the-holy-spirit.html",
    "context": {
      "title": "Goodness Born and Borne of the Holy Spirit",
      "first_heading": "Goodness Born and Borne of the Holy Spirit"
    }
  },
  {
    "path": "blog-gospel-centered-runners-part-1.html",
    "context": {
      "title": "Gospel-Centered Runners- Part 1",
      "first_heading": "Gospel-Centered Runners- Part 1"
    }
  },
  {
    "path": "blog-gospel-centered-runners-part-2.html",
    "context": {
      "title": "Gospel Centered Runners Part-2",
      "first_heading": "Gospel Centered Runners Part-2"
    }
  },
  {
    "path": "blog-hold-on-it-s-not-the-end.html",
    "context": {
      "title": "Hold On It's Not The End",
      "first_heading": "Hold On It's Not The End"
    }
  },
  {
    "path": "blog-jabez-s-prayer-to-extend-god-s-territory.html",
    "context": {
      "title": "Jabez\u2019s Prayer to Extend God\u2019s Territory",
      "first_heading": "Jabez\u2019s Prayer to Extend God\u2019s Territory"
    }
  },
  {
    "path": "blog-jesus-roadshow-in-jerusalem.html",
    "context": {
      "title": "JESUS\u2019 ROADSHOW IN JERUSALEM!",
      "first_heading": "JESUS\u2019 ROADSHOW IN JERUSALEM!"
    }
  },
  {
    "path": "blog-joy-born-and-borne-of-the-holy-spirit.html",
    "context": {
      "title": "JOY BORN AND BORNE OF THE HOLY SPIRIT",
      "first_heading": "JOY BORN AND BORNE OF THE HOLY SPIRIT"
    }
  },
  {
    "path": "blog-jude-contend-for-the-faith.html",
    "context": {
      "title": "Jude- Contend for the Faith",
      "first_heading": "Jude- Contend for the Faith"
    }
  },
  {
    "path": "blog-judgement-that-is-cradled-in-the-gospel-of-jesus-christ.html",
    "context": {
      "title": "Judgement that is cradled in the Gospel of Jesus Christ",
      "first_heading": "Judgement that is cradled in the Gospel of Jesus Christ"
    }
  },
  {
    "path": "blog-kindness-born-and-borne-of-the-holy-spirit.html",
    "context": {
      "title": "KINDNESS BORN AND BORNE OF THE HOLY SPIRIT",
      "first_heading": "KINDNESS BORN AND BORNE OF THE HOLY SPIRIT"
    }
  },
  {
    "path": "blog-kingdom-citizenship-impacting-earthly-citizenship.html",
    "context": {
      "title": "KINGDOM CITIZENSHIP IMPACTING EARTHLY CITIZENSHIP",
      "first_heading": "KINGDOM CITIZENSHIP IMPACTING EARTHLY CITIZENSHIP"
    }
  },
  {
    "path": "blog-knowing-the-author-of-our-salvation.html",
    "context": {
      "title": "Knowing the Author of our Salvation",
      "first_heading": "Knowing the Author of our Salvation"
    }
  },
  {
    "path": "blog-laodecia-a-church-in-which-jesus-needed-to-re-enter.html",
    "context": {
      "title": "Laodecia: A church in which Jesus needed to re-enter",
      "first_heading": "Laodecia: A church in which Jesus needed to re-enter"
    }
  },
  {
    "path": "blog-living-as-the-children-of-light.html",
    "context": {
      "title": "Living As The Children Of Light",
      "first_heading": "Living As The Children Of Light"
    }
  },
  {
    "path": "blog-love-born-and-borne-of-the-holy-spirit.html",
    "context": {
      "title": "LOVE BORN AND BORNE OF THE HOLY SPIRIT",
      "first_heading": "LOVE BORN AND BORNE OF THE HOLY SPIRIT"
    }
  },
  {
    "path": "blog-patience-born-and-borne-of-the-holy-spirit.html",
    "context": {
      "title": "PATIENCE BORN AND BORNE OF THE HOLY SPIRIT",
      "first_heading": "PATIENCE BORN AND BORNE OF THE HOLY SPIRIT"
    }
  },
  {
    "path": "blog-peace-born-and-borne-of-the-holy-spirit.html",
    "context": {
      "title": "Peace Born and Borne Of The Holy Spirit",
      "first_heading": "Peace Born and Borne Of The Holy Spirit"
    }
  },
  {
    "path": "blog-peter-the-weak-rock.html",
    "context": {
      "title": "Peter: The Weak Rock!",
      "first_heading": "Peter: The Weak Rock!"
    }
  },
  {
    "path": "blog-philadelphia-little-strength-backed-by-a-great-god.html",
    "context": {
      "title": "Philadelphia: Little Strength backed by a Great God",
      "first_heading": "Philadelphia: Little Strength backed by a Great God"
    }
  },
  {
    "path": "blog-reprogrammed-by-the-gospel.html",
    "context": {
      "title": "Reprogrammed by the Gospel",
      "first_heading": "Reprogrammed by the Gospel"
    }
  },
  {
    "path": "blog-rescued-to-recall-and-rejoice-celebrating-the-lord-s-table.html",
    "context": {
      "title": "RESCUED TO RECALL AND REJOICE- CELEBRATING THE LORD\u2019s TABLE",
      "first_heading": "RESCUED TO RECALL AND REJOICE- CELEBRATING THE LORD\u2019s TABLE"
    }
  },
  {
    "path": "blog-respect-that-is-characteristic-of-the-gospel.html",
    "context": {
      "title": "RESPECT THAT IS CHARACTERISTIC OF THE GOSPEL",
      "first_heading": "RESPECT THAT IS CHARACTERISTIC OF THE GOSPEL"
    }
  },
  {
    "path": "blog-responding-to-conflict-within-and-without-a-gospel-centered-approach.html",
    "context": {
      "title": "Responding to Conflict \u2018Within\u2019 and \u2018Without\u2019- A Gospel Centered Approach",
      "first_heading": "Responding to Conflict \u2018Within\u2019 and \u2018Without\u2019- A Gospel Centered Approach"
    }
  },
  {
    "path": "blog-sardis-godly-on-the-outside-godless-on-the-inside.html",
    "context": {
      "title": "SARDIS: GODLY ON THE OUTSIDE GODLESS ON THE INSIDE",
      "first_heading": "SARDIS: GODLY ON THE OUTSIDE GODLESS ON THE INSIDE"
    }
  },
  {
    "path": "blog-the-ark-that-rescues.html",
    "context": {
      "title": "The Ark That Rescues",
      "first_heading": "The Ark That Rescues"
    }
  },
  {
    "path": "blog-the-church-called-to-live-an-un-compromised-life.html",
    "context": {
      "title": "The Church Called To Live An Un-compromised Life",
      "first_heading": "The Church Called To Live An Un-compromised Life"
    }
  },
  {
    "path": "blog-the-empty-tomb-dead-or-alive.html",
    "context": {
      "title": "The Empty Tomb: Dead Or Alive?",
      "first_heading": "The Empty Tomb: Dead Or Alive?"
    }
  },
  {
    "path": "blog-the-eye-opener.html",
    "context": {
      "title": "The Eye Opener",
      "first_heading": "The Eye Opener"
    }
  },
  {
    "path": "blog-the-finger-that-refused-to-condemn.html",
    "context": {
      "title": "The Finger That Refused To Condemn",
      "first_heading": "The Finger That Refused To Condemn"
    }
  },
  {
    "path": "blog-the-genesis-of-bethlehem.html",
    "context": {
      "title": "The Genesis of Bethlehem",
      "first_heading": "The Genesis of Bethlehem"
    }
  },
  {
    "path": "blog-the-gospel-echo-in-the-workplace-work-that-worships.html",
    "context": {
      "title": "The gospel echo in the workplace: work that worships",
      "first_heading": "The gospel echo in the workplace: work that worships"
    }
  },
  {
    "path": "blog-the-gospel-takes-birth-a-miraculous-conception.html",
    "context": {
      "title": "The Gospel Takes Birth: A Miraculous Conception",
      "first_heading": "The Gospel Takes Birth: A Miraculous Conception"
    }
  },
  {
    "path": "blog-the-gospel-takes-birth-at-bethlehem-god-takes-center-stage.html",
    "context": {
      "title": "The Gospel Takes Birth: At Bethlehem God Takes Center Stage",
      "first_heading": "The Gospel Takes Birth: At Bethlehem God Takes Center Stage"
    }
  },
  {
    "path": "blog-the-gospel-takes-birth-everybody-ought-to-know-who-jesus-is-though-born-in-a-manger.html",
    "context": {
      "title": "The Gospel Takes Birth: Everybody Ought to Know Who Jesus Is- Though Born In A Manger",
      "first_heading": "The Gospel Takes Birth: Everybody Ought to Know Who Jesus Is- Though Born In A Manger"
    }
  },
  {
    "path": "blog-the-gospel-takes-birth-part-of-a-predicament-or-part-of-a-purpose.html",
    "context": {
      "title": "The Gospel Takes Birth: PART OF A PREDICAMENT OR PART OF A PURPOSE",
      "first_heading": "The Gospel Takes Birth: PART OF A PREDICAMENT OR PART OF A PURPOSE"
    }
  },
  {
    "path": "blog-the-greatest-command-the-command-to-love.html",
    "context": {
      "title": "The Greatest Command- The Command To Love",
      "first_heading": "The Greatest Command- The Command To Love"
    }
  },
  {
    "path": "blog-the-i-am-of-the-winds-and-the-waters.html",
    "context": {
      "title": "THE \u2018I AM\u2019 OF THE WINDS AND THE WATERS",
      "first_heading": "THE \u2018I AM\u2019 OF THE WINDS AND THE WATERS"
    }
  },
  {
    "path": "blog-the-mimic-and-the-model-for-jesus-christ.html",
    "context": {
      "title": "The Mimic and The Model For Jesus Christ",
      "first_heading": "The Mimic and The Model For Jesus Christ"
    }
  },
  {
    "path": "blog-the-psalm-of-simeon.html",
    "context": {
      "title": "The Psalm Of Simeon",
      "first_heading": "The Psalm Of Simeon"
    }
  },
  {
    "path": "blog-the-relevance-of-follow-me-in-our-present-times.html",
    "context": {
      "title": "The Relevance of \u201cFollow Me\u201d in our Present Times",
      "first_heading": "The Relevance of \u201cFollow Me\u201d in our Present Times"
    }
  },
  {
    "path": "blog-the-way-of-the-messenger-impacts-the-message.html",
    "context": {
      "title": "The Way Of The Messenger Impacts The Message",
      "first_heading": "The Way Of The Messenger Impacts The Message"
    }
  },
  {
    "path": "blog-thorns-for-a-crown-a-cross-for-a-throne.html",
    "context": {
      "title": "Thorns for a Crown a Cross for a Throne",
      "first_heading": "Thorns for a Crown a Cross for a Throne"
    }
  },
  {
    "path": "blog-thyatira-a-church-tolerant-of-seduction-within.html",
    "context": {
      "title": "THYATIRA: A CHURCH TOLERANT OF SEDUCTION WITHIN",
      "first_heading": "THYATIRA: A CHURCH TOLERANT OF SEDUCTION WITHIN"
    }
  },
  {
    "path": "blog-when-god-pursues-with-mercy.html",
    "context": {
      "title": "WHEN GOD PURSUES WITH MERCY",
      "first_heading": "WHEN GOD PURSUES WITH MERCY"
    }
  },
  {
    "path": "blog-when-god-rejoices-in-repentance.html",
    "context": {
      "title": "WHEN GOD REJOICES IN REPENTANCE",
      "first_heading": "WHEN GOD REJOICES IN REPENTANCE"
    }
  },
  {
    "path": "blog-when-god-s-mercy-and-grace-gives-second-invitations.html",
    "context": {
      "title": "WHEN GOD\u2019s MERCY AND GRACE GIVES SECOND INVITATIONS",
      "first_heading": "WHEN GOD\u2019s MERCY AND GRACE GIVES SECOND INVITATIONS"
    }
  },
  {
    "path": "blog-when-god-s-mercy-moves-beyond-boundaries.html",
    "context": {
      "title": "WHEN GOD\u2019s MERCY MOVES BEYOND BOUNDARIES",
      "first_heading": "WHEN GOD\u2019s MERCY MOVES BEYOND BOUNDARIES"
    }
  },
  {
    "path": "blog-when-sinless-hands-touched-sinful-feet.html",
    "context": {
      "title": "When Sinless Hands Touched Sinful Feet",
      "first_heading": "When Sinless Hands Touched Sinful Feet"
    }
  },
  {
    "path": "contact-us.html",
    "context": {
      "title": "Crossroad South Church | Contact Us",
      "first_heading": "CONTACTUS"
    }
  },
  {
    "path": "css/4ba1f7eeea678c518b19a8a229705620.css",
    "context": {
      "path": "css/4ba1f7eeea678c518b19a8a229705620.css"
    }
  },
  {
    "path": "css/559e64bf161e61fa0aca6e864c78191d.css",
    "context": {
      "path": "css/559e64bf161e61fa0aca6e864c78191d.css"
    }
  },
  {
    "path": "css/7e610f95a2d26c26bc901487cdcd9a1c.css",
    "context": {
      "path": "css/7e610f95a2d26c26bc901487cdcd9a1c.css"
    }
  },
  {
    "path": "css/84d4a0216f16f715d9b301db3a8da352.css",
    "context": {
      "path": "css/84d4a0216f16f715d9b301db3a8da352.css"
    }
  },
  {
    "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css",
    "context": {
      "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css"
    }
  },
  {
    "path": "css/d09d646f062b67daeff66ff1410b63fc.css",
    "context": {
      "path": "css/d09d646f062b67daeff66ff1410b63fc.css"
    }
  },
  {
    "path": "css/internal-styles.css",
    "context": {
      "path": "css/internal-styles.css"
    }
  },
  {
    "path": "gallery.html",
    "context": {
      "title": "Crossroad South Church | Gallery",
      "first_heading": "VIDEOGALLERY"
    }
  },
  {
    "path": "give.html",
    "context": {
      "title": "Crossroad South Church | Give",
      "first_heading": "GIVE"
    }
  },
  {
    "path": "imgs/015269adc941c55077d19dda6bbbfdcd.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/04cd26a7e71848a5ebf8e88a2669b63b.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/0525e299afe46b90ffd029547aac7026.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0528bb9ca1e12c2bb084c80d84cc0801.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/06af1f2ec3cd6cf1f3700f7ccc15bed9.webp",
    "context": {
      "refs": [
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07fdff9edd48463c4573c33f782a7e97.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0b32641db7745af52088f24e2d44d0d7.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/0c00292e23598f1d21e440d53f7e09c8.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/116073250e5423b7ed6cbb008373d14a.webp",
    "context": {
      "refs": [
        {
          "alt": "Benjamin Stephen, Pastor In-Charge",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/16b12c6b7dacd6048ac834ddaaac251e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1a03b428e4b3c5d2d2a16a35b3376912.webp",
    "context": {
      "refs": [
        {
          "alt": "Corporate Worship",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1a7f5a841a782a47b6e38ca1be10bcb1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1b03561771239b8a6eb7b9f02f081bd3.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/208efa9d18f4e8c996fddbdec4594f10.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/2145b8f08fd29ba59ecf7f360c4f565b.webp",
    "context": {
      "refs": [
        {
          "alt": "Core Values",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/29529a7e3ef5241dcd9d324b9d3f3ddd.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/29af004223c4b3257730101d2124e212.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e4599b3c5ce4a85e6ada0e4e410c81c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/371cd9c4752fd50d6a72cd0cba994035.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/38c0871e5e0dcab5bf287f46c0444daf.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/3e39582987706d41db721482687f8a62.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/42ff88518db6ad22ff582c521018e7ff.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/476ca60dce8069b6e68180bcd03c5811.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c0d7ff3000c92b7f64a384add000cf6.webp",
    "context": {
      "refs": [
        {
          "alt": "Teens Ministry",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c8997667541a7a38b824197ebe20a7e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4e2aca67a59f3fb55eb6308dec7b1f32.webp",
    "context": {
      "refs": [
        {
          "alt": "Our Vision",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/50b3d964f0785d3a450831ea1a4b7308.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/50d672ad36e60845467523c603c5ad73.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/54120b9e107fcc4a3e335243be673283.webp",
    "context": {
      "refs": [
        {
          "alt": "Kingdom Warriors",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5a2d8bf39a0a22454bff87ac135d08d7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5bcaeb74b55be9956e8414e68352489b.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/5f20f2f7924f06fdd6cc3c8b1ef0887f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/64554838275f777c2b0cba9f5a6a06ee.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6ed1e669b309939ed817bf65e03c602e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7180500aceadf8aeeaf2f9ee1ea72003.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/744730eb82c5b8834327374a6cb9ac8a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/778ce088b476a3490d58caa02448e0e9.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/78983f7026fe95e3d9a60450c74a42b7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7d0ea75bade7391a2f7cc0371faeb11e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/809d6ea327bf2e3c5cab4b298ffee655.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/8226f2f4dc825354d52d588d0a7858cf.webp",
    "context": {
      "refs": [
        {
          "alt": "Our Mission",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/827bd1cd7f33c2fa1d06c051aea19196.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/86390458ed9812dd913590e589bf7338.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86a4d17ea861184b3747180228b99a13.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/87da342e3d87e5c7b091f489c4a8b959.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8835b9d83d7f9987cbb8e9986d178e2d.webp",
    "context": {
      "refs": [
        {
          "alt": "Timothy Connors, Elder-Pastor",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/88a7b350c318c63d2104a45845a0890f.webp",
    "context": {
      "refs": [
        {
          "alt": "Crossroad South Church",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8ce09e79604e34c31faee32b1acd2bd5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/90ea54af805f598625c3285bff3f9dff.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/98d048157833e846710898487cf450dc.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/9cce5de697c41bb1a861b397d0a159e4.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/a0cf85e77efb98bf545c7b1f76a11a23.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/a490f104164a21f043b30ed302f2b591.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/a5a39c525206760a7fbf6e10c1d05841.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a82000ab1f9b4f14d52869b2366c0245.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a84c042ec0f62f19946f6a2d14354235.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a84ee5730d243dcc0a45d88f7b742159.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ac9197856310146e0f623282bed2eb37.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b0dc1228f2c289cb6d03084943206cf0.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/b0f80b53f59fa75a8f912c74f69c79c2.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b5721aca08135b6e061e17fae4016faa.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/b794547df644dc49700302d39a02d05e",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b9832ce1e3dabce86326d05cacb89f43.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/bc26b60905a3cde8bd01d4872187a47a.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/be7b3ee99b12fa939c35a0e1c9b6c367.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/be7c7e9d6b7f806a437bb42c93bb29ac.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c0d1cf5c964993f9c81f9bbb6c95b1d3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c1d1b4d71c65c983deaf3e1092e02d52.webp",
    "context": {
      "refs": [
        {
          "alt": "Womens Ministry",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c1ec2177520de19f711646ff95f865e6.svg",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/cfeac0ccc141595ced8df7cc5e336a9b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d0e036e87d8beb4f2b77b0de70bab3d4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d1c453a77596d3cf6159b91aa5ac738e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d1c6ef342cb994da44fbd1e9a26f1746.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d85654748ce3c98af0b2f40bd77d9989.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d8e4eabef9d29466c8ce99e91c4a66df.webp",
    "context": {
      "refs": [
        {
          "alt": "What follows is our understanding of basic \u201cessentials\u201d of the biblical, orthodox Christian faith. W",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dc8ad9184ec085407231c4f251fd167d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e523fe11889d5cf8f18418a67bb31f8f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e55cfbd8e873d74784f8aeab648a2ede.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e58ff5d788c04653d6398aff5ff06702.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e9f1cb9c37db9a908d82be04c61f0988.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ed2a246d80e3f32dbbcda8a8ee004583.webp",
    "context": {
      "refs": [
        {
          "alt": "We are a community of Christ-followers from diverse linguistic, geographic, and cultural backgrounds",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ef14331603d10754a7f85ab9469172fb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f82aba01ae8c50cfbda40dd59268a0f9.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/f9d46bea5fe7deb48ca5bc74dcd0d878.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "index.html",
    "context": {
      "title": "Crossroad South Church | Home",
      "first_heading": "Welcome to Crossroad South Church!"
    }
  },
  {
    "path": "js/03b2eaae6007054a68c38e495f894dba.js",
    "context": {
      "path": "js/03b2eaae6007054a68c38e495f894dba.js"
    }
  },
  {
    "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js",
    "context": {
      "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js"
    }
  },
  {
    "path": "js/0c46896987137b0016246f6bc2243099.js",
    "context": {
      "path": "js/0c46896987137b0016246f6bc2243099.js"
    }
  },
  {
    "path": "js/165d7b0ddfa33362140feea997351b77.js",
    "context": {
      "path": "js/165d7b0ddfa33362140feea997351b77.js"
    }
  },
  {
    "path": "js/16df9ef05001a1741857bf99f5a5738f.js",
    "context": {
      "path": "js/16df9ef05001a1741857bf99f5a5738f.js"
    }
  },
  {
    "path": "js/2a85c11e395a8380b5915443e926b569.js",
    "context": {
      "path": "js/2a85c11e395a8380b5915443e926b569.js"
    }
  },
  {
    "path": "js/34be5330971fdbd18985525bd994b0aa.js",
    "context": {
      "path": "js/34be5330971fdbd18985525bd994b0aa.js"
    }
  },
  {
    "path": "js/35c5f9e096d4da33d2a62031daf14248.js",
    "context": {
      "path": "js/35c5f9e096d4da33d2a62031daf14248.js"
    }
  },
  {
    "path": "js/3d70953a848219e749fedc2cdb906675.js",
    "context": {
      "path": "js/3d70953a848219e749fedc2cdb906675.js"
    }
  },
  {
    "path": "js/3e940a33e44b65c1c0af8bb80a893530.js",
    "context": {
      "path": "js/3e940a33e44b65c1c0af8bb80a893530.js"
    }
  },
  {
    "path": "js/544d012df7acf9c3f0920f67c9e322b9.js",
    "context": {
      "path": "js/544d012df7acf9c3f0920f67c9e322b9.js"
    }
  },
  {
    "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js",
    "context": {
      "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js"
    }
  },
  {
    "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js",
    "context": {
      "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js"
    }
  },
  {
    "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js",
    "context": {
      "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js"
    }
  },
  {
    "path": "js/7260bab328b0ad74815a5efb377bcc67.js",
    "context": {
      "path": "js/7260bab328b0ad74815a5efb377bcc67.js"
    }
  },
  {
    "path": "js/893de96f1b6da546bd7c814964723eca.js",
    "context": {
      "path": "js/893de96f1b6da546bd7c814964723eca.js"
    }
  },
  {
    "path": "js/8fb17a140b7a8d358403cadeea2d2bec.js",
    "context": {
      "path": "js/8fb17a140b7a8d358403cadeea2d2bec.js"
    }
  },
  {
    "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js",
    "context": {
      "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js"
    }
  },
  {
    "path": "js/9455859483e31e4da0e28f10d0742c2a.js",
    "context": {
      "path": "js/9455859483e31e4da0e28f10d0742c2a.js"
    }
  },
  {
    "path": "js/9db10375d298678e53777a2347b87073.js",
    "context": {
      "path": "js/9db10375d298678e53777a2347b87073.js"
    }
  },
  {
    "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js",
    "context": {
      "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js"
    }
  },
  {
    "path": "js/a2261649751fa61b606222c9b2ea3b80.js",
    "context": {
      "path": "js/a2261649751fa61b606222c9b2ea3b80.js"
    }
  },
  {
    "path": "js/b0bade6d42c2702ca85774296cc507c4.js",
    "context": {
      "path": "js/b0bade6d42c2702ca85774296cc507c4.js"
    }
  },
  {
    "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js",
    "context": {
      "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js"
    }
  },
  {
    "path": "js/cecb447a04bbe3e8982190dd6e697120.js",
    "context": {
      "path": "js/cecb447a04bbe3e8982190dd6e697120.js"
    }
  },
  {
    "path": "js/d80b370d82680fc786dcc943a327b9f2.js",
    "context": {
      "path": "js/d80b370d82680fc786dcc943a327b9f2.js"
    }
  },
  {
    "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js",
    "context": {
      "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js"
    }
  },
  {
    "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js",
    "context": {
      "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js"
    }
  },
  {
    "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js",
    "context": {
      "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js"
    }
  },
  {
    "path": "sermons.html",
    "context": {
      "title": "Crossroad South Church | Sermons",
      "first_heading": "OURSERMONS"
    }
  },
  {
    "path": "worship.html",
    "context": {
      "title": "Crossroad South Church | Workship Service",
      "first_heading": "OURWORSHIP SERVICE"
    }
  }
]

Return only a JSON object mapping each path to its new basename (same extension). No other text.