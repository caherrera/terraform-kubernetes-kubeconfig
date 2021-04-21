# terraform-kubernetes-kubeconfig
Generate kubeconfig files with Terraform

## Example

```hcl
module "kubeconfig" {
  source  = "redeux/kubeconfig/kubernetes"
  version = "0.0.2"

  current_context = "kind-kind"
  clusters = [{
    "name" : "kind-kind",
    "server" : "https://127.0.0.1:53851",
    certificate_authority_data = "LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUN5RENDQWJDZ0F3SUJBZ0lCQURBTkJna3Foa2lHOXcwQkFRc0ZBREFWTVJNd0VRWURWUVFERXdwcmRXSmwKY201bGRHVnpNQjRYRFRJeE1EUXlNVEExTURVeU4xb1hEVE14TURReE9UQTFNRFV5TjFvd0ZURVRNQkVHQTFVRQpBeE1LYTNWaVpYSnVaWFJsY3pDQ0FTSXdEUVlKS29aSWh2Y05BUUVCQlFBRGdnRVBBRENDQVFvQ2dnRUJBTnE1ClE0N205dHpTQzhjVnpxYUVUN24zOGdPQi9MMkdtb0VUbFllRG1KazBUWTFWQnZ3QjA4OTc2NnovcHhqMGs3bVMKTTlacmhMYkhNcUVaWTllZ3NNcDVxbHNkV0xMbFkvNFY4a1l6TWp6Vjd4NXdtM0tSa3h6NUJRaXJIWHFyeS93WApwNlpha3dCQTZycXNJSW5Kd29WYVQwNXFQVHhxQmpEN09RL1V1VFNwUVBpVmZOYjZKL2lRZWQ4eG9LaGpKU05WCkc3SGNCQjZodVdoOHNVSFdnUGZydGp4Y1ZlUDlwSytDMEJ0SDBEL0V4cjc4RmdLTzRhL2RSVk5lN1JiTlQ0aG0KM0pxSG9TMXZpdkJsSUdpQTYyalNqVFVIRmxCUXowbmxlR1VBTEllcEIyNXlJR3l6ZnVxY2YyRlZyVUYxRStZaQpDZTh5NVhoY1I2RkV0bHhWZnJFQ0F3RUFBYU1qTUNFd0RnWURWUjBQQVFIL0JBUURBZ0trTUE4R0ExVWRFd0VCCi93UUZNQU1CQWY4d0RRWUpLb1pJaHZjTkFRRUxCUUFEZ2dFQkFHUHFiRjU0Zk5kNmo1ZTMyZThjZGV3U2hZa0wKQzJiWVVicTFaNk9ic05iM3pHOTRucUYyaFArdWdobHBudFRqaWkwV04zbW5zOFY3cUlkOE1RQm0wRDVVNi94SAp4K3EzcW5TWm95VUd6R3I5UjloempKN3ovWCt4TUYxT0xsTEZnTTljZGhTdFhyajJNWSthTTdzMjFBQy8wU2NVCmtabjcvdzN6MnRCTExFVlNpQ1dXeDc0eEl5bExQTUovaFhRRHNuYUtmTEhSeXVtalNXVTdPZ1I1Q1FLeXJEQXMKenJjU0Z0Z0dPYmJoellDVDlWK1dIU0Q0dGZONFQwbFdhU3dDTXNOUmkzQ3lOV1EzZy9GSWNmOGszWGt0VXdjLwpiVnAxV2VJak04VjBibWN6V2pLNmkvR0dqZUVKRW5oZkkzdi9WZGxKc3ljR3YwODVpMTNuRFF6dTgvbz0KLS0tLS1FTkQgQ0VSVElGSUNBVEUtLS0tLQo="
  }]
  contexts = [{
    "name" : "kind-kind",
    "cluster_name" : "kind-kind"
    "user" : "kind-kind"
  }]
  users = [{
    "name" : "",
    "client_certificate_data" : "LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUM4akNDQWRxZ0F3SUJBZ0lJWjFvaWJPR3dwakF3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TVRBME1qRXdNalF3TWpKYUZ3MHlNakEwTWpFd01qUXdNalJhTURReApGekFWQmdOVkJBb1REbk41YzNSbGJUcHRZWE4wWlhKek1Sa3dGd1lEVlFRREV4QnJkV0psY201bGRHVnpMV0ZrCmJXbHVNSUlCSWpBTkJna3Foa2lHOXcwQkFRRUZBQU9DQVE4QU1JSUJDZ0tDQVFFQXdsMENqQTlsUnNqWDV1ckoKeHNMUm4ybFRlL3Z0VFRuN0dCN0xUbE1STlc3RFp0Zk0wVjhSZGZ4OGRRSzY2TXU1MEIxelYvR3BvS2JmaEI0bwpNR2JMVnlxQVQxQVl0azhwWGMxSUUwb2psKzkrL1Fxd1J5S0hDN2UyeFdSRnhHL2hlK2E4bHZPY3gxVFJWWDNKCnIzVUM5NXh1alVvMElnZ1pCT3NwYzl3emNaZzl0emZoTkVjZDZPTEg3ZDlGT3FTd0ZPNDdRUUhnSW5mUXlvRWEKYmgxUDdsMHM4SXBxWFJWbjZMcHg4bXpVUUwzRjEvc2pqemdiYTNSemo2Qm1pUGYwWlFxZHN1VktFNExReWo2MAovTzEwck51bjhpcGdCUjN1V0drSy9QdmtibVlob2FnSXNSbWRwNnVsK1RVMEV2RzIwcEFFeGJxNEhJeS9nT09qCkc1dzdNd0lEQVFBQm95Y3dKVEFPQmdOVkhROEJBZjhFQkFNQ0JhQXdFd1lEVlIwbEJBd3dDZ1lJS3dZQkJRVUgKQXdJd0RRWUpLb1pJaHZjTkFRRUxCUUFEZ2dFQkFBTzZOelk2MTJseGxEbmFhYk5iVjNvcFRGUmZ3R2IwQ084VQpvS1BYWlJWVWp5YkkwWnA5QTQ4MGNmTHI2ejM5T3c2R25Jb3BwbTJWeFB2ZTBRVEVJYTEvcmRrcExFRXdBa1llCjlpWE1UNGdqNUt6VUpVNHRRSmRnRFhkVnRuRTZKUllOT0s2amFvK2VsQk5WSko3b3IwNjFRbTZWOFBvc2ZqdWcKUjN0Mm5LakJpWEZoRHRGVXhxWHoxSWxKT3VvcURmbUIrblZOQXhHYXM3bTNQT2Z3by9TcVJYclZBQTNmVE02KwpidXZSR3ZsK0Q0UVRVSThGbFpLV2tUZlBoZkhidE5zckw3NWQrMmp3aTFlWU1TMWJaMHlqOGgrcEp0ang4aDBMCk0rbmhxTlB5L0RzeURCZFlhUEluWW0wSTI4UytFU0FEdHJGTGZydjBkT2xOalhIb2ZaWT0KLS0tLS1FTkQgQ0VSVElGSUNBVEUtLS0tLQo="
    "client_key_data" : "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFcEFJQkFBS0NBUUVBd2wwQ2pBOWxSc2pYNXVySnhzTFJuMmxUZS92dFRUbjdHQjdMVGxNUk5XN0RadGZNCjBWOFJkZng4ZFFLNjZNdTUwQjF6Vi9HcG9LYmZoQjRvTUdiTFZ5cUFUMUFZdGs4cFhjMUlFMG9qbCs5Ky9RcXcKUnlLSEM3ZTJ4V1JGeEcvaGUrYThsdk9jeDFUUlZYM0pyM1VDOTV4dWpVbzBJZ2daQk9zcGM5d3pjWmc5dHpmaApORWNkNk9MSDdkOUZPcVN3Rk80N1FRSGdJbmZReW9FYWJoMVA3bDBzOElwcVhSVm42THB4OG16VVFMM0YxL3NqCmp6Z2JhM1J6ajZCbWlQZjBaUXFkc3VWS0U0TFF5ajYwL08xMHJOdW44aXBnQlIzdVdHa0svUHZrYm1ZaG9hZ0kKc1JtZHA2dWwrVFUwRXZHMjBwQUV4YnE0SEl5L2dPT2pHNXc3TXdJREFRQUJBb0lCQUhIbEZ3MEVLSkRtT0w1MApiM0V0MExEZGc3SnYyb3Nhb3UxcmZpK1R0YzNkN2x0aHNnQXUrWWh1UUhCQS9VNVZzN2treU9hTUVwNjFxdDA4CjNzZ2VOS0lMb2N6WVh1TFdXS05ESEMxUmtMSUVBaUkrRlRaYUlWRFlneDRBdUhGNExtWHd2Q3FvN3dKUHphdVAKWHBTV3VQcG9qTS8yMzczaGlPZTg5am1TbkFLLzhSYlFlRFFJWUVPK1NwRjBCVWVJRGdwRGNtTzFWaFNXYU5ZSwpGNVc4a2ROMFhXVjJILzk3S0EvQStxaHlhT3FGWUdLTzVwV2RWK3o1Q2NNcDJ2NWNVTVQ1WU1zVFJaZ2x2YXJwClhFa3dzRnJmaTkrQ3dkVUtnZWdHZWJCTTU3czg2RnpLckFnNFBLMXZja1lBeFlseG9zdWM1dnlJMlFhYWxDbTMKQk52MkF5RUNnWUVBOWk4THpuc0JwTEN3MHZEUVZCdXk4allvd05pOVVBR01hUDRWVUFTM1BCR09KaHY0K3h2MApDZHBoM1ZYd2VXeVBYSXczaDd4K0kwNkVwM0tTNTU0b1pjL1BqZCtvZnNiOGh4cm4yZFNteGEzVzZjejhRRXc3CjlFUkpBY2hqcUs5YlV5UHRaRUNnd0VWQVhkMm1XNm15UUJvQlQ0dUlLeWxiK3dLM1FrU0x5VDBDZ1lFQXloei8KNWNxdDFZQ2Z0NERYT1FsUG5XRE5JRmVob255NFZhb0JUNWxXNGRCeTN1QXJpc21hRFJ5YXNOMlFzTFQrOVBZNwpLWFZTeFFsSGJGeXp0RDVhZEhoclhYRFNGSzZMb3BySnMrcnhVbm16SWdqUnBRUXQ1VjdjaWNseEhnUGJnZTJDCnNpMjdDZUFWekpkQ0ZVVWZ0Smw0S052cVFSOGJ5cEg5ZFpkbC9TOENnWUVBbE9wU2J2MHpPa2J6UHpZU0hyNSsKbVVzdmphL05uRWJEZzRNbXF6ZWZDMFBuUTZBcUZPT00xQ1Q0aStWL1NFUGwyR3FzOEh1UnBaUEtaR3ZHOXpwUgpYM3k4SlNyRWhxT2hmNnhEMFIxMElDR08zZkIwS2dTelE0Zkd6Y0JFb0hZcWZQay9rU1FTMlJ0SzJ6ekhjNjBMCnVRRENDRGIwRUgrOU52SW1ubnhPUGxVQ2dZQW44K0dWOENHNjBhbEE0Z1FwYnpEQXdIRHNFc2FOMHkreEoyRUkKOWh2Wm1aWUxmcTY4eWF0ZEtpbGVDdjVlSC9sQ1BTWm14SjF1KzYyVnV5Ris0TkNLczM4dHdtNlV6Z2dtUllqWAp1dnFuUGcxdURlWTdRMzg3Rnl4clJGbkxBQ0kxSmRrdkZhRWlpNXhqakFieEkyL29DR3BiVVZXV04rc0xlUjVzClQxaEcyd0tCZ1FDR3ZPTW1CV1VlWjJTMmxlQTJhcjJZOHl4T0Q2dkh6L09ucWpjQjRRdnZCMFlxWjFsWEh4azcKYUNHNFdNTi9GYWRta2gzM213MjZkbkRGWDI3eW5rTGkwTFdZQXFXeGFBMHpYK1BUUVAyVTZRRDdLNmUvZUtKRApPem5IM09pMTYyY05uRDBNcGxCcXRKTWFYODFHbVpJK0llNHNqdm51aUdoQnl3bFdhYkxwUFE9PQotLS0tLUVORCBSU0EgUFJJVkFURSBLRVktLS0tLQo="
    }, {
    "name" : "kind-kind",
    "client_certificate_data" : "LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUM4akNDQWRxZ0F3SUJBZ0lJTWVqdkdCbzRVeFF3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TVRBME1qRXdOVEExTWpkYUZ3MHlNakEwTWpFd05UQTFNamxhTURReApGekFWQmdOVkJBb1REbk41YzNSbGJUcHRZWE4wWlhKek1Sa3dGd1lEVlFRREV4QnJkV0psY201bGRHVnpMV0ZrCmJXbHVNSUlCSWpBTkJna3Foa2lHOXcwQkFRRUZBQU9DQVE4QU1JSUJDZ0tDQVFFQXhVemFRbUw3dzRvZ2hDa2sKTTlSbGJBM2FrNnhzaFM5L25JcFpWTytYSDJYL2xLNnJjTEVlbzZuMlZqRmNGNmRxUzdOUlIraXdBUlh4Mm9PSQpmcjBjSXhOV0RDckdGMlB4c2pXRWp3VElRUHhseERBeU80cS9jZ2V0ZW5GUjZ0NU0xQkhyNWgvbjdrTjU4K0V2Ckt6bm9lbUVKOVU4YzhaMDVuN21KWVhpVkJmYlhXY0c0a0hlZkNVeGFPTGdJTGdkZHROUlplZ1I2NnBrbkk3TGMKMzZnYWxzVjJPbzViZ01rbURpbVp5Mko2TVZVcHZWMFhkSFBWaEllNHRHWTlFSEVCcUtESnd4YXRqeUozQWZEVgp2UlVadm1HY1d1WmVYeFVCVklBVWxxMllMQlhjN28xaXpwcnFYMG1ScGVvc1hrdEhCY0p0bFZOemlncWVzRGhqCk5QL0tmUUlEQVFBQm95Y3dKVEFPQmdOVkhROEJBZjhFQkFNQ0JhQXdFd1lEVlIwbEJBd3dDZ1lJS3dZQkJRVUgKQXdJd0RRWUpLb1pJaHZjTkFRRUxCUUFEZ2dFQkFCeE9xOU5iWEw0NGltU3hOdnF5YjRGTGZVUjNReUc0VkpTMwpsUFhNY2U5OGdmYnladmJZeWF3RmR0by9Ua2xTOE1YNjRIOTVOQjhMTzZtNW9kTE1ZNnZzSkYyRHpMR3I4b0JJCkdnV0ZWSUVHNGtKRVAzejJIeFd1bFovRmlDVis4QXBDZ2dIdTh3VWI5ekdoM0JocmtDZTQ0ci91NkorUlNIa0oKZ2NXaGpWZm9mdjArbDBiZ3hNblcxZlRnN3pjdzBXQmVhTVV3T283SWFkcXFSRm1JSHNyRWUzUWRiQ1p5by94RwovTXpFZ3FPY2VFK283ang4NmVwZStvbjdwVERnS01jUmROTXFCNWMzTWhGbHVLQTQ2RFREK3V2cUREMWFtbjBWCjVnQ1ZUbktGeS8wbEwwV3IxcnlvaFdlSDFpVGlRMVVyZXlKcGg2MU8xZ002N25JajlIdz0KLS0tLS1FTkQgQ0VSVElGSUNBVEUtLS0tLQo="
    "client_key_data" : "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFcEFJQkFBS0NBUUVBeFV6YVFtTDd3NG9naENra005UmxiQTNhazZ4c2hTOS9uSXBaVk8rWEgyWC9sSzZyCmNMRWVvNm4yVmpGY0Y2ZHFTN05SUitpd0FSWHgyb09JZnIwY0l4TldEQ3JHRjJQeHNqV0Vqd1RJUVB4bHhEQXkKTzRxL2NnZXRlbkZSNnQ1TTFCSHI1aC9uN2tONTgrRXZLem5vZW1FSjlVOGM4WjA1bjdtSllYaVZCZmJYV2NHNAprSGVmQ1V4YU9MZ0lMZ2RkdE5SWmVnUjY2cGtuSTdMYzM2Z2Fsc1YyT281YmdNa21EaW1aeTJKNk1WVXB2VjBYCmRIUFZoSWU0dEdZOUVIRUJxS0RKd3hhdGp5SjNBZkRWdlJVWnZtR2NXdVplWHhVQlZJQVVscTJZTEJYYzdvMWkKenBycVgwbVJwZW9zWGt0SEJjSnRsVk56aWdxZXNEaGpOUC9LZlFJREFRQUJBb0lCQVFDaklrUmxGOHJyaDA0VAplS0VDYWQvaVZDSWljRExhZk1lYSs1bVpiUEViZVE2Mk5TWno2ejlXTzdYKzFwazZ4YVpTS1ZaUGlzbmNXL1M1CnBJQTdxc21WQnV2aTY0c1cxQUNJUlUveG9SYWpCUTV3QlJuRHVabEtBNmNnMG9uVkZUR1pONmhCZ3FnV2paeE0KVmlqV0tPOWNJTmhIQ0w3NTEvSkphdk40c0djbm9kZ2NvV05MazM1LzlOK2RZTzVEcURKSDM4UUZ0eXZqZ2ZRSwpERi9XNjQrd3VYSDVOSUVnNjFaQU1FRlVuRlQ3YTh5bTN0TGFDbldpRFdxTFR5Mmk2T0FQc01qak5FcHVvWExlCld4WHlNS09SbzJDbjl2WERwRUV4RzluN0hLSHR2dnFhRitPNXRkRjBsdTU5M2RxelN3QUVENHpJbU9CT2tWWlcKN05MZGIzMVJBb0dCQVBqeWduM2RLZ1J5VTl6TVg3UkNrTUNrcVhOSnFLQ0JhZ2RUNlkwdTB4Z1MxNEhreVdaMgpyand6YzExcTBjcDF6RHFXOVJJZ3hvTGVqUUpyYmFXcWFEb3VCaXNQTmF2MGJoc3hmTm5VL1hrQVFaRFFrcmkwCk14ZU1xR1FNaHhqZjU4dWR6NmlWbjJFeS96elJyei9YNFFRZXMrenFzY1JERDM4cnorb0FKLzcvQW9HQkFNcmoKeGJPeHh6ZGMvMEhVYlphOHhwUEQ4aE5yOXR2dHk3VllVUVdaS0NCTHd3SGZMWXJCU3NpeEtmNGxETlZXenl5MApVNXFOd3NEM3RzL0s5T0lTQVc3ZURrbHJkWnNjYy96Z05ENFBRUUVnVzQ5eUdqWGc0WXpiVnVqZ2hGckc2YTFZCkl4VlJmQ0tSb2xJcEp3WEVLYnNTK2NtTlh2UlpYREdRRWxUcHhiS0RBb0dBVFFRaGtMVENVZnZZcS85aVFFOHoKbnhXU0FzT3Y4bS8zRUd0S1hzNDBxa2J4K3hKL3FENWhLdWl6OFJ1aDZhUEYyZjVudFFNRXh1bjQ3OTJ5WDBVMwoxMy96a3BDekJ3Nm9uYXNTdUFWbm9XNk4yakpjb2QzRnpLeE1VQjk4RUJyOUNBWTdmeWxDMUh4RmNGaGlnanJVCk4wVVVYdUJBdkxvT2FrWnduVEVOTHBzQ2dZQmxqVHB3cGdSRDVzMXhBc1hUbEN1RTNLZjNKcXdLQ3UxU21LRDkKUDFyQlI0cVZEa002VjJONkxvc0pSVHcyTUZ4RVVRSWpzdDhQUFM0SXRkcDZxVzZFTXF0Ti9uYUFLKzYyWFBacApOYk5ndi9SMFNUVnJVR00wNExpUW1ZaEY4NWdWQnErUXhSZHdLaHJvS3ViNFVPWmVWN0lsT3hpVEQ0TkEzNDc5Clo0Rm54d0tCZ1FEdUx6WXd0SkYvckc2dEV4THZ3U3ZLMWQ0UVI2TDZVaHh2NHRnU2k1anlLQytUeUtiakNPSUEKdEZJTk1HbWY2em5BaDlwQVBLd0VKSDlPVDY5bUR3bjh6TnlrZUxZQmZNYlRrcEdqSkRuSEdjaWVkUjJBbXRqdgpBQVNXQVhNY2FWUkpFVXhVLzFrWjBUUnZsR1J3K0psdDhodDZvdWZ2dGZueDlpc01sUmxrN0E9PQotLS0tLUVORCBSU0EgUFJJVkFURSBLRVktLS0tLQo="
  }]
}
```

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >=0.15.0 |
| <a name="requirement_local"></a> [local](#requirement\_local) | >=2.0.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_local"></a> [local](#provider\_local) | >=2.0.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [local_file.kubeconfig](https://registry.terraform.io/providers/hashicorp/local/latest/docs/resources/file) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_clusters"></a> [clusters](#input\_clusters) | List of cluster configurations | <pre>set(object({<br>    name                       = optional(string)<br>    server                     = optional(string)<br>    certificate_authority      = optional(string)<br>    certificate_authority_data = optional(string)<br>    insecure_skip_tls_verify   = optional(bool)<br>  }))</pre> | n/a | yes |
| <a name="input_colors"></a> [colors](#input\_colors) | Colors | `bool` | `true` | no |
| <a name="input_contexts"></a> [contexts](#input\_contexts) | List of context configurations | <pre>set(object({<br>    name         = optional(string)<br>    cluster_name = optional(string)<br>    namespace    = optional(string)<br>    user         = optional(string)<br>  }))</pre> | n/a | yes |
| <a name="input_current_context"></a> [current\_context](#input\_current\_context) | Context name | `string` | `""` | no |
| <a name="input_filename"></a> [filename](#input\_filename) | Filename | `string` | `"kubeconfig"` | no |
| <a name="input_users"></a> [users](#input\_users) | List of user configurations | <pre>set(object({<br>    name                    = optional(string)<br>    username                = optional(string)<br>    password                = optional(string)<br>    token                   = optional(string)<br>    client_certificate      = optional(string)<br>    client_key              = optional(string)<br>    client_certificate_data = optional(string)<br>    client_key_data         = optional(string)<br>  }))</pre> | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_kubeconfig_content"></a> [kubeconfig\_content](#output\_kubeconfig\_content) | HCL representation of kubeconfig file contents |
| <a name="output_kubeconfig_path"></a> [kubeconfig\_path](#output\_kubeconfig\_path) | Path to the kubeconfig file |