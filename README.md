# meetreader
A library to parse documents containing the results of swimming meets and represent them in a standard format


## The idea
    meetreader.src('http://www.collegeswimming.us/results/28723/150318P001.htm')
      .parse(['meetreader-hytec-html', 'meetreader-hytec-pdf'])
      .then(console.log, console.error);

would output

    {
      source_file: "http://www.collegeswimming.us/results/28723/150318P001.htm",
      file_generated: "2015-03-18 10:47 AM",
      file_parsed: "2015-12-03 2:37 PM",
      meet_name: "NCAA Division III Championships",
      start_date: "2015-03-18",
      end_date: "2015-03-21",
      description: "Hosted by City of Shenandoah and SCAC; Conroe ISD Natatorium",
      license: "Woodforest Natatorium - Site License",
      events: [
        {
          event_number: 1,
          gender: "Women",
          stroke: "Freestyle",
          distance: 500,
          units: "Yards",
          historical_swims: [
            {
              label: "NCAA Record",
              time: 283.37,
              date: "2011-02-23",
              name: "Kendra Stern",
              team: "Amherst"
            },
            {
              label: "Meet Qualify",
              time: 298.37
            },
            {
              label: "2014 Winner",
              time: 288.19,
              name: "Sarah Thompson",
              team: "Williams"
            },
          ],
          result_sets: [
            {
              type: "Preliminaries",
              results: [
                {
                  rank: 1,
                  surname: "Thompson",
                  given_name: "Sarah",
                  age: "SR",
                  team: "Williams",
                  seed_time: 296.40,
                  finish_time: 287.67,
                  splits: [
                    {
                      from: 0,
                      to: 50,
                      time: 25.84,
                      cuumulative: 25.84
                    },
                    {
                      from: 50,
                      to: 100,
                      time: 27.72,
                      cuumulative: 53.56
                    },
                    ...
                  ]
                },
                ...
              ]
            }
          ]
        }
      ]
    }
