# procstat

displays linux proc stat (/proc/pid/stat) in human-readable format

# summary

Small tool to translate cryptic info from /proc/\[pid\]/stat into
understandable form. Actually, ps shows most of things needed. But this will
show you everything at once in mostly raw format.

Read man 5 proc about meaning of fields.

Obsolete and unmaintained fields (which will always show a zero value) are
named `obs_<fieldname>`, all other fields are named to match the original
field names (as per man 5 proc).

Should correctly handle all /proc/\[pid\]/stat fields as of Linux 2.6.24.

Without arguments procstat reads stat info from stdin.

# example

    ./procstat $(pidof bash)
                      pid: 190910
                     comm: bash
                    state: S
                     ppid: 20565
                     pgid: 190910
                      sid: 190910
                   tty_nr: 34853
                    tpgid: 194918
                    flags: 0000000000400000
                   minflt: 8906
                  cminflt: 24743
                   majflt: 0
                  cmajflt: 0
                    utime: 0d  0:00:00 (0.110000)
                    stime: 0d  0:00:00 (0.050000)
                   cutime: 0d  0:00:00 (0.230000)
                   cstime: 0d  0:00:00 (0.150000)
                 priority: 20
                     nice: 0
              num_threads: 1
          obs_itrealvalue: 0d  0:00:00 (0.000000)
                starttime: 2023-07-27T10:55:31+1000 (3181.84s)
                    vsize: 13078528
                      rss: 1527
                   rsslim: 9223372036854775807
                startcode: 94063588659200
                  endcode: 94063589572365
               startstack: 140733782370032
                  kstkesp: 0
                  kstkeip: 0
                   signal: 0000000000000000
                  blocked: 0000000000010000
                sigignore: 0000000000384004
                 sigcatch: 000000004b813efb
                    wchan: 1
                obs_nswap: 0
               obs_cnswap: 0
              exit_signal: 0000000000000011
                processor: 3
              rt_priority: 0
                   policy: SCHED_OTHER
    delayacct_blkio_ticks: 0d  0:00:00 (0.000000)
               guest_time: 0d  0:00:00 (0.000000)
              cguest_time: 0d  0:00:00 (0.000000)

# thanks

Original code: http://brokestream.com/procstat.html

Forked from: https://github.com/vjardin/procstat
