
dk ezctl backup default
ansible-playbook -i clusters/default/hosts -e @clusters/default/config.yml playbooks/94.backup.yml
2025-02-25 11:25:18 INFO cluster:default backup begins in 5s, press any key to abort:


PLAY [localhost] **********************************************************************************************************************************

TASK [Gathering Facts] ****************************************************************************************************************************
ok: [localhost]

TASK [set NODE_IPS of the etcd cluster] ***********************************************************************************************************
ok: [localhost]

TASK [get etcd cluster status] ********************************************************************************************************************
changed: [localhost]

TASK [debug] **************************************************************************************************************************************
ok: [localhost] => {
    "ETCD_CLUSTER_STATUS": {
        "changed": true,
        "cmd": "for ip in 10.10.10.100 ;do ETCDCTL_API=3 /etc/kubeasz/bin/etcdctl --endpoints=https://\"$ip\":2379 --cacert=/etc/kubeasz/clusters/default/ssl/ca.pem --cert=/etc/kubeasz/clusters/default/ssl/etcd.pem --key=/etc/kubeasz/clusters/default/ssl/etcd-key.pem endpoint health; done",
        "delta": "0:00:00.396815",
        "end": "2025-02-25 11:25:36.653236",
        "failed": false,
        "msg": "",
        "rc": 0,
        "start": "2025-02-25 11:25:36.256421",
        "stderr": "",
        "stderr_lines": [],
        "stdout": "https://10.10.10.100:2379 is healthy: successfully committed proposal: took = 115.095776ms",
        "stdout_lines": [
            "https://10.10.10.100:2379 is healthy: successfully committed proposal: took = 115.095776ms"
        ]
    }
}

TASK [get a running ectd node] ********************************************************************************************************************
changed: [localhost]

TASK [debug] **************************************************************************************************************************************
ok: [localhost] => {
    "RUNNING_NODE.stdout": "10.10.10.100"
}

TASK [get current time] ***************************************************************************************************************************
changed: [localhost]

TASK [make a backup on the etcd node] *************************************************************************************************************
changed: [localhost]

TASK [update the latest backup] *******************************************************************************************************************
changed: [localhost]

PLAY RECAP ****************************************************************************************************************************************
localhost                  : ok=9    changed=5    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0  